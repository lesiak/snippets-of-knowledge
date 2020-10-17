# 
* [WITH Queries (Common Table Expressions)](https://www.postgresql.org/docs/9.1/static/queries-with.html)
* [PostgreSQL’s CTEs are optimisation fences](https://blog.2ndquadrant.com/postgresql-ctes-are-optimization-fences/)
* [Index Types](https://www.postgresql.org/docs/9.2/static/indexes-types.html)
* [GIN and GiST Index Types](https://www.postgresql.org/docs/current/static/textsearch-indexes.html)

* [Advisory Locks](https://www.postgresql.org/docs/9.1/static/functions-admin.html)
* [13.3.4. Advisory Locks](https://www.postgresql.org/docs/9.1/static/explicit-locking.html#ADVISORY-LOCKS)
* [Advisory Locks and How to Use Them](http://shiroyasha.io/advisory-locks-and-how-to-use-them.html)
* [Advisory Locks in PostgreSQL](https://hashrocket.com/blog/posts/advisory-locks-in-postgres)

* Rest metrics: host:20443/rest/cluster_overview/json

# Storing lists
I recently added a new list to my entity, which needed to be persisted in my POSTGRES database.
I wondered if how many available ways of storing it would compare against an obvious approach of creating a new table.

My assumptions:
- the list will contain short strings
- the list will also be short, approx ~15 items max
- I will only ecaluate postgres

I would need to perform following operations:
- get multiple without filtering on a list
- get multiple with 'contains' filter on a list
- get one
- set list on the entity.

My app:
- I will use JOOQ to query the database
- Hence, the support of querying constructs in JOOQ matters
- The ease ifquerying in plain SQL matters
- This will never be a high-profile app, but I will evaluate efficiency anyway

Here are the ways of storing the list I came up with:
- Separate table
- Plain text column with comma-separated values
- jsonb column not json (https://www.postgresql.org/docs/9.4/datatype-json.html)
- array column
- hstore column

# Json Column

```
create table rabbits_json (
  rabbit_id bigserial primary key, 
  name text, 
  info jsonb not null
);
insert into rabbits_json (name, info) values
  ('Henry','["lettuce","carrots"]'),
  ('Herald','["carrots","zucchini"]'),
  ('Helen','["lettuce","cheese"]');
```

### Select
https://stackoverflow.com/questions/19925641/check-if-a-postgres-json-array-contains-a-string
```
select * from rabbits_json where info ? 'carrots';
```

### JOOQ Mapping
```
public class RabbitsJson implements Serializable {
  private static final long serialVersionUID = 1467721205;

    private final Long   rabbitId;
    private final String name;
    private final JSONB  info;
    //...
}
```

### Select via JOOQ

by default transformed to JSONB wrapper, which warape a string.
You can implement your own binding, though: https://stackoverflow.com/questions/27044702/how-to-insert-a-updatable-record-with-json-column-in-postgresql-using-jooq

I think this is not supported in JOOQ yet

https://github.com/jOOQ/jOOQ/issues/7242
https://github.com/jOOQ/jOOQ/issues/8944
https://github.com/jOOQ/jOOQ/issues/8950
https://github.com/jOOQ/jOOQ/issues/9997

But you can drop to native query
https://stackoverflow.com/questions/25068563/jooq-postgres-json-query

https://stackoverflow.com/questions/64338474/howto-expose-a-native-sql-function-as-a-predicate



# Array

https://www.postgresql.org/docs/9.1/arrays.html

create table rabbits_array (
  rabbit_id bigserial primary key, 
  name text, 
  info text[] not null
);
insert into rabbits_array (name, info) values
  ('Henry','{"lettuce","carrots"}'),
  ('Herald','{"carrots","zucchini"}'),
  ('Helen','{"lettuce","cheese"}');

### JOOQ mapping
```
public class RabbitsArray implements Serializable {

    private static final long serialVersionUID = 2126679703;

    private final Long     rabbitId;
    private final String   name;
    private final String[] info;

```

good!

### Querying via SQL
https://stackoverflow.com/questions/39643454/postgres-check-if-array-field-contains-value/39643544

select * from rabbits_array where 'carrots' =ANY(info)
select * from rabbits_array where info @> ARRAY['carrots', 'lettuce']

### Querying via JOOQ
Elegant if the field is varchar[]
```
var rabbits = dslContext.selectFrom(Tables.RABBITS_ARRAY)
                                        .where(Tables.RABBITS_ARRAY.INFO.contains(new String[]{"carrots"}))
```
Infortunately, if the field is text[], it needs a workaround as it is a bug:
https://github.com/jOOQ/jOOQ/issues/4754


# modifying value:
```
dslContext.update(Tables.RABBITS_ARRAY)
                  .set(Tables.RABBITS_ARRAY.INFO, new String[]{"carrots", "lettuce", "pumpkin"})
                  .where(Tables.RABBITS_ARRAY.NAME.equal("Henry"))
                  .execute();
```