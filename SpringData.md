* [What is JdbcDaoSupport used for?](http://stackoverflow.com/questions/21519940/what-is-jdbcdaosupport-used-for/)

JdbcDaoSupport, NamedParameterJdbcDaoSupport, SimpleJdbcDaoSupport are unnecessary and are mental dust. They doesn't save any line of code because you need to inject data-source or template into.

What I recommend - to create templates in XML/class config per data source and reuse/inject them as templates are thread safe according to docs:

* [Spring @Transactional and JDBC autoCommit](http://stackoverflow.com/questions/16301315/spring-transactional-and-jdbc-autocommit)

# ORM
* [How to inject JPA EntityManager using spring](http://stackoverflow.com/questions/2421339/how-to-inject-jpa-entitymanager-using-spring)
* [How to get JPA configured with Spring 3?](http://stackoverflow.com/questions/5373035/how-to-get-jpa-configured-with-spring-3/)
* [PersistenceUnit vs PersistenceContext](http://stackoverflow.com/questions/21038706/persistenceunit-vs-persistencecontext)

I don't know how it works exactly in the Java EE, but in Spring, when you specify @PersistenceContext annotation, it injects EntityManager. Where does it get EntityManager? It is wrong to create one EntityManager for the whole application lifetime by calling EntityManagerFactory.createEntityManager(). So instead a special implementation of EntityManager interface is used and instantiated directly. It has an internal mutable thread-local reference to a real EntityManager. Implementations of methods just redirect calls to this real EntityManager. And there is a servlet listener, that before each request obtain EM by calling EMF.createEntityManager() and assign it to that inner reference of special EM. Also this listener manages transactions by calling getTransaction().begin(), .commit() and .rollback() on the real EM. It is very simplified description of performed work. And I believe, that JEE container does the same thing, as Spring does.

In general case it is better to inject EntityManager, because with EntityManagerFactory and @PersistenceUnit you should create/destroy EntityManager every time by hands and manage transactions too.

* [What is difference between CrudRepository and JpaRepository interfaces in Spring Data JPA](http://stackoverflow.com/questions/14014086/what-is-difference-between-crudrepository-and-jparepository-interfaces-in-spring)
* [Spring Data JPA - “No Property Found for Type” Exception](http://stackoverflow.com/questions/19583540/spring-data-jpa-no-property-found-for-type-exception)

* [Configuring Spring Boot for Oracle](https://springframework.guru/configuring-spring-boot-for-oracle/)
* [Spring Boot + Spring Data JPA + Oracle example](https://www.mkyong.com/spring-boot/spring-boot-spring-data-jpa-oracle-example/)