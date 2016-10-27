# Dependency Injection
* [SPRING INJECTION WITH @RESOURCE, @AUTOWIRED AND @INJECT](http://blogs.sourceallies.com/2011/08/spring-injection-with-resource-and-autowired/)

> When I looked under the hood I determined that the ‘@Autowired’ and ‘@Inject’ annotation behave identically. Both of these annotations use the ‘AutowiredAnnotationBeanPostProcessor’ to inject dependencies. ‘@Autowired’ and ‘@Inject’ can be used interchangeable to inject Spring beans. However the ‘@Resource’ annotation uses the ‘CommonAnnotationBeanPostProcessor’ to inject dependencies. Even though they use different post processor classes they all behave nearly identically. Below is a summary of their execution paths.
 
**@Autowired and @Inject**
> 1. Matches by Type
> 2. Restricts by Qualifiers
> 3. Matches by Name

**@Resource**
> 1. Matches by Name
> 2. Matches by Type
> 3. Restricts by Qualifiers (ignored if match is found by name)

* [Spring @Component, @Repository, @Service and @Controller Annotations](http://howtodoinjava.com/spring/spring-core/how-to-use-spring-component-repository-service-and-controller-annotations/)
* [Difference between Spring @Component, @Service, @Repository, @Controller](http://latest-tutorial.com/2015/01/19/difference-spring-component-service-repository-controller/)

### @Bean annotated methods produce singletons by default
Spring in Action, pg 45
> Spring will intercept any calls to it and ensure that the bean produced by that method (@Bean annotated) is returned
rather than allowing it to be invoked again.

> By default, all beans in Spring are singletons


> To avoid referring to a bean by calling its method.
This approach to referring to other beans is usually the best choice

* [Difference between using bean id and name in Spring configuration file](http://stackoverflow.com/questions/874505/difference-between-using-bean-id-and-name-in-spring-configuration-file)


# Thymeleaf expressions ${} vs *{}:

The ${} expressions (such as ${spitter}) are variable
expressions. Normally, these are Object-Graph Navigation Language (OGNL)
expressions (http://commons.apache.org/proper/commons-ognl/). But when used
with Spring, they’re SpEL expressions. In the case of ${spitter}, it resolves to the
model property whose key is spitter.
As for *{} expressions, they’re selection expressions. Whereas variable expressions
are evaluated against the entire SpEL context, selection expressions are evaluated on
a selected object.

# Spring Mvc
* [Simplest Spring MVC Hello World Example](http://crunchify.com/simplest-spring-mvc-hello-world-example-tutorial-spring-model-view-controller-tips/)

# ORM
* [How to inject JPA EntityManager using spring](http://stackoverflow.com/questions/2421339/how-to-inject-jpa-entitymanager-using-spring)
* [How to get JPA configured with Spring 3?](http://stackoverflow.com/questions/5373035/how-to-get-jpa-configured-with-spring-3/)
* [PersistenceUnit vs PersistenceContext](http://stackoverflow.com/questions/21038706/persistenceunit-vs-persistencecontext)

I don't know how it works exactly in the Java EE, but in Spring, when you specify @PersistenceContext annotation, it injects EntityManager. Where does it get EntityManager? It is wrong to create one EntityManager for the whole application lifetime by calling EntityManagerFactory.createEntityManager(). So instead a special implementation of EntityManager interface is used and instantiated directly. It has an internal mutable thread-local reference to a real EntityManager. Implementations of methods just redirect calls to this real EntityManager. And there is a servlet listener, that before each request obtain EM by calling EMF.createEntityManager() and assign it to that inner reference of special EM. Also this listener manages transactions by calling getTransaction().begin(), .commit() and .rollback() on the real EM. It is very simplified description of performed work. And I believe, that JEE container does the same thing, as Spring does.

In general case it is better to inject EntityManager, because with EntityManagerFactory and @PersistenceUnit you should create/destroy EntityManager every time by hands and manage transactions too.

* [What is JdbcDaoSupport used for?](http://stackoverflow.com/questions/21519940/what-is-jdbcdaosupport-used-for/)

JdbcDaoSupport, NamedParameterJdbcDaoSupport, SimpleJdbcDaoSupport are unnecessary and are mental dust. They doesn't save any line of code because you need to inject data-source or template into.

What I recommend - to create templates in XML/class config per data source and reuse/inject them as templates are thread safe according to docs: