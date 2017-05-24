# Thymeleaf 


## Expressions ${} vs *{}:

The ${} expressions (such as ${spitter}) are variable
expressions. Normally, these are Object-Graph Navigation Language (OGNL)
expressions (http://commons.apache.org/proper/commons-ognl/). But when used
with Spring, they’re SpEL expressions. In the case of ${spitter}, it resolves to the
model property whose key is spitter.
As for *{} expressions, they’re selection expressions. Whereas variable expressions
are evaluated against the entire SpEL context, selection expressions are evaluated on
a selected object.