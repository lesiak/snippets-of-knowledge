# Maven

* [Maven Recipe: Building an aggregate jar](https://rombertw.wordpress.com/2010/05/14/maven-recipe-building-an-aggregate-jar/)
* [How to Create Two JARs from One Project (...and why you shouldn't)](http://blog.sonatype.com/2010/01/how-to-create-two-jars-from-one-project-and-why-you-shouldnt/) - explains that one output artifact per project is a core assumption of Maven, and thus going against it is a bad idea.

# The library cannot be released, maven source plugin is executed twice.
As a result sources-jar artifact is uploaded to nexus twice, which fails.

Used
mvn -Prelease-profile help:effective-pom
to check that maven source plugin is attached to 2 goals: jar and jar-no-fork
(See: http://stackoverflow.com/questions/4251488/maven-release-plugin-fails-source-artifacts-getting-deployed-twice)

Maven 3.0.5 accepted this, but a bug in Maven 3.2.3-3.3.9 causes the sources artifact to be deployed twice, which is rejected by nexus.
See: https://issues.apache.org/jira/browse/MNG-5939
See also: https://issues.apache.org/jira/browse/MNG-5940
The issue is fixed in Maven 3.4.0, but it is not released yet.

There are 2 possible workarounds for this:
- downgrade Maven to 3.0.x or 3.1.x
- attach jar goal in maven-source-plugin to non-existing phase (http://blog.soebes.de/blog/2016/07/01/spoiler-alert-maven-3-dot-4-0-changes-ii/)

