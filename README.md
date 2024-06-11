# Aggregated descriptions of personal projects

## [install-mgmt](https://github.com/fabcaz/install-mgmt)

### Goal:

Personal project similar to SFG [Microservice course](https://www.udemy.com/course/spring-boot-microservices-with-spring-cloud-beginner-to-guru) but self guided to better grasp:
 - Domain-Driven-Design
 - N-tier architecture
 - Deployment
 - Application Security

### Description:

Application to manage the life cycle of an equipment installation request.

Work in progress.


## [reactive-notes-app](https://github.com/fabcaz/reactive-notes-app)

### Goal:
  * Gain deeper understanding of Spring by creating a project without the SpringBoot autoconfigurations
  * Experience Reactive programming
  * Learn some SQL by creating own queries instead of relying on SpringData query derivation

### Description:

Notes application with different domain objects for different types of notes (e.g. a note on a video or one on a blog or forum post), implemented using 

Originally intended to be used with the [miniature-broccoli](https://github.com/fabcaz/miniature-broccoli) pages, but was abandoned in favor of: 
1. Using vim and grep to manage notes
2. Going back to SpringBoot to focus on other aspect of development

## [miniature-broccoli](https://github.com/fabcaz/miniature-broccoli)

### Goal:

To gain some familiarity with front end fundamentals.

### Description:

Main page with a navbar, a sidebar containing category nested dropdowns, and existing notes in the center.
Note creation page using \<template\>s to add new components in some note sections (submitForm() needs to called from console since the submit button was not implemented).

## [csv-mapper](https://github.com/fabcaz/small-csv-mapper)

### Goal:

To convert a csv format from one software product to a different csv format recognized by another product. I was initially going to use an awk script but the complexity of the conversion ultimately made java a more attractive option.

### Description:
Some types of entries mapped directly to the desired format, but others first needed to be merged into an intermediary format.

i.e. (a,b,c,d) -> (1,2) where:
- map({a,b}) -> {1} 
- merge({c,d}) -> {"two"} then map({"two"}) -> {2}

The steps were 1) substitute label names, 2) substitute headers, 3) rearrange columns, 4) merge types that require merging.

For convenience, (1) was done directly with a text editor.

Since (2) and (3) could be achieved simply by constructing a different object, instead of being consistent and constructing an intermediary object for all types in the source csv, some types directly converted to the target type; only the types that needed to be merged in (4) were merged into an intermediary object.

## [api-to-csv-script](https://github.com/fabcaz/sturdy-garbanzo)

### Goal:

While using a software product, I needed to get data from a web site which has an API. I chose to create a python script to get the data from the API and save it in a csv format recognized by the software product. I configured a logger and read config data from a separate file for educational purposes.

### Description:

#### small script that:

- configures a logger
- reads args from yaml file
- finds every n<sup>th</sup> date in a given interval
- requests data for each date from an API
- writes the data to a csv file

## ms-komb-*

### Description:

Set of projects mainly following along the following SFG courses:

* [Microservices course](https://www.udemy.com/course/spring-boot-microservices-with-spring-cloud-beginner-to-guru)
* [Maven course](https://www.udemy.com/course/apache-maven-beginner-to-guru/)
* [Spring Boot Test course](https://www.udemy.com/course/testing-spring-boot-beginner-to-guru/)


projects include:

* [komb-ITcontainers](https://github.com/fabcaz/komb-ITcontainers) - Docker containers and sample DB data to integration test projects following along SFG's [Microservices](https://www.udemy.com/course/spring-boot-microservices-with-spring-cloud-beginner-to-guru), [Spring Boot Test](https://www.udemy.com/course/testing-spring-boot-beginner-to-guru/), and [Maven](https://www.udemy.com/course/apache-maven-beginner-to-guru/) courses

* [ms-komb-order-service](https://github.com/fabcaz/ms-komb-order-service) - SpringBoot microservice application managing orders for an ecommerce; part of a set of projects following along SFG's [Microservices](https://www.udemy.com/course/spring-boot-microservices-with-spring-cloud-beginner-to-guru), [Spring Boot Test](https://www.udemy.com/course/testing-spring-boot-beginner-to-guru/) courses. It uses Spring State Machine to manage order status and Eventual Consistency, and interacts with other microservices asynchronously via Java Message Service. [Click here](https://github.com/fabcaz/ms-komb-order-service/blob/master/src/main/resources/static/diagrams/sm-state-diagram.png) for state machine diagram created using PlantULM.

* [kombucha-ms-bom](https://github.com/fabcaz/kombucha-ms-bom) - Incorporated a part of the [Maven course](https://www.udemy.com/course/apache-maven-beginner-to-guru/) into the [Microservices course](https://www.udemy.com/course/spring-boot-microservices-with-spring-cloud-beginner-to-guru) projects by extracting common dependencies into a BOM uploaded to [packagecloud](https://packagecloud.io/kombuchamaster/release).

## [perma_coop](https://github.com/fabcaz/perma_coop)

### Goal:
To gain some understanding of how the Ethereum blockchain actually works

### Description:

This project is a simple ecommerce app with the backend meant to be deployed on the
Ethereum blockchain, and a basic frontend to interact with the smart contract.

It uses [mugen's diamond1](https://github.com/mudgen/diamond-1) for modularity and upgradability.
It also uses openzeppelin's AccessControl and ERC20 contracts which have
been added as diamond facets.

The Market contract manages the inventory but would need to be rewritten as a
proxy to act more like a simple crud repository; mainly to allow for upgradability.
