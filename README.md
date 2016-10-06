# Maven

* [Maven Recipe: Building an aggregate jar](https://rombertw.wordpress.com/2010/05/14/maven-recipe-building-an-aggregate-jar/)
* [How to Create Two JARs from One Project (...and why you shouldn't)](http://blog.sonatype.com/2010/01/how-to-create-two-jars-from-one-project-and-why-you-shouldnt/) - explains that one output artifact per project is a core assumption of Maven, and thus going against it is a bad idea.

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

# Spring Mvc
* [Simplest Spring MVC Hello World Example](http://crunchify.com/simplest-spring-mvc-hello-world-example-tutorial-spring-model-view-controller-tips/)
