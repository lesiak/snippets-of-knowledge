# Spring
* [SPRING INJECTION WITH @RESOURCE, @AUTOWIRED AND @INJECT](http://blogs.sourceallies.com/2011/08/spring-injection-with-resource-and-autowired/)

 When I looked under the hood I determined that the ‘@Autowired’ and ‘@Inject’ annotation behave identically. Both of these annotations use the ‘AutowiredAnnotationBeanPostProcessor’ to inject dependencies. ‘@Autowired’ and ‘@Inject’ can be used interchangeable to inject Spring beans. However the ‘@Resource’ annotation uses the ‘CommonAnnotationBeanPostProcessor’ to inject dependencies. Even though they use different post processor classes they all behave nearly identically. Below is a summary of their execution paths.

**@Autowired and @Inject**
1. Matches by Type
2. Restricts by Qualifiers
3. Matches by Name

**@Resource**
1. Matches by Name
2. Matches by Type
3. Restricts by Qualifiers (ignored if match is found by name)

* [Spring @Component, @Repository, @Service and @Controller Annotations](http://howtodoinjava.com/spring/spring-core/how-to-use-spring-component-repository-service-and-controller-annotations/)
* [Difference between Spring @Component, @Service, @Repository, @Controller](http://latest-tutorial.com/2015/01/19/difference-spring-component-service-repository-controller/)

# Spring in Action, pg 45
@Bean, Spring will
intercept any calls to it and ensure that the bean produced by that method is returned
rather than allowing it to be invoked again.

By default, all beans in Spring are singletons


To avoid referring to a bean by calling its method.
This approach to referring to other beans is usually the best choice

nothing that says the CompactDisc bean even needs to be
declared in JavaConfig; it could have been discovered by component scanning or
declared in XML
@Bean
public CDPlayer cdPlayer(CompactDisc compactDisc) {
return new CDPlayer(compactDisc);
}


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
