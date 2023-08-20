# Eureka! Clinical Common Web Application Framework
[Andrew Post](http://www.andrewrpost.com), Salt Lake City, UT

Derived from software previously developed by me and my team at the [Georgia Clinical and Translational Science Alliance (Georgia CTSA)](http://www.georgiactsa.org), [Emory University](http://www.emory.edu), Atlanta, GA

## What does it do?
It implements a custom web application development framework that uses best of breed components:
* Google Guice 3.0 (dependency injection)
* Jersey 1.19.4 (REST)
* Hibernate 5.0.12.Final (object-relational mapping)
* Tomcat 7

It supports calling these components through the standard APIs specified in and provided by the [Eureka! Clinical Web Application Standard APIs project](https://github.com/eurekaclinical/eurekaclinical-standard-apis).

It extends the functionality in the [Eureka! Clinical Web Application Standard APIs project](https://github.com/eurekaclinical/eurekaclinical-standard-apis) with the following features and implementations:
* REST communication objects for users, roles, groups and authorization templates (`org.eurekaclinical.common.comm`)
* Base classes for implementing REST clients (`org.eurekaclinical.common.comm.clients`)
* Base classes for implementing Guice modules (`org.eurekaclinical.common.config`)
* Servlet filters for user authorization (`org.eurekaclinical.common.filter`)
* Servlets for login and logout; destroying a session; and proxying (`org.eurekaclinical.common.servlet`)

See [Structure of Eureka! Clinical microservices](https://github.com/eurekaclinical/dev-wiki/wiki/Structure-of-Eureka%21-Clinical-microservices) for how to use the framework. The goal for the version 2.0 release is for all Eureka! Clinical web application components to use this framework.

Latest release: [![Latest release](https://maven-badges.herokuapp.com/maven-central/org.eurekaclinical/eurekaclinical-common/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.eurekaclinical/eurekaclinical-common)

## Version 4.1
* Added a missing class from the auto-authorization work,
  ProxyingServiceServletModuleWithAutoAuthorization, for services that
  need to connect to other services.

## Version 4.0
* Fully implement auto-authorization.

## Version 3.0
* Removed RolesFromServiceFilter because Eureka! Clinical webapps no longer need role information.
* Removed WebappServletModule, which was superceded by APIGatewayServletModule.
* Removed AbstractAuthorizingServletModule and AbstractAuthorizingJerseyServletModule, which are unused.
* Add POST and PUT calls for passing a string into an Eureka! Clinical API gateway proxy.
* Require version 2.1 or greater of eurekaclinical-standard-apis.


## Version 2.0
The goal of the 2.0 series is to have sufficient functionality for all Eureka! Clinical web applications to depend on eurekaclinical-common.

## Version 1.0
Implemented partial functionality, and only some parts of Eureka! Clinical used it.

## Build requirements
* [Oracle Java JDK 8](http://www.oracle.com/technetwork/java/javase/overview/index.html)
* [Maven 3.2.5 or greater](https://maven.apache.org)

## Runtime requirements
* [Oracle Java JRE 8](http://www.oracle.com/technetwork/java/javase/overview/index.html)
* [Tomcat 7](https://tomcat.apache.org)

## Building it
The project uses the maven build tool. Typically, you build it by invoking `mvn clean install` at the command line. For simple file changes, not additions or deletions, you can usually use `mvn install`. See https://github.com/eurekaclinical/dev-wiki/wiki/Building-Eureka!-Clinical-projects for more details.

## Maven dependency
```
<dependency>
    <groupId>org.eurekaclinical</groupId>
    <artifactId>eurekaclinical-common</artifactId>
    <version>version</version>
</dependency>
```

## Developer documentation
* [Javadoc for latest development release](http://javadoc.io/doc/org.eurekaclinical/eurekaclinical-common) [![Javadocs](http://javadoc.io/badge/org.eurekaclinical/eurekaclinical-common.svg)](http://javadoc.io/doc/org.eurekaclinical/eurekaclinical-common)
* [Javadoc for version 3.0](http://javadoc.io/doc/org.eurekaclinical/eurekaclinical-common/3.0)

## Getting help
Feel free to contact us at help@eurekaclinical.org.
