---
layout: post
title:  "Spring Boot Data Repository Elastic Search"
date:   2020-04-15 1:25:00 +1000
categories: Geek
---

Spring Data Elasticsearch is the solution using Elasticsearch Search Engine. It provide

- `Templates` as high-level abstraction for storing, quering, sorting and faceting documents.

- `Repositories` provide a interface to define customized method to do query search.

**Configuration**

We could start from the Configuration.

Step 1. Define repositories using `@EnableElasticsearchRepositories` annotation

- Use basePackages to define entry point to scan repository interface definition. 

Step 2. Define all related bean you need

- RestHighLevelClient setup connection to ES

- EntityMapper make the customized mapping from your application to ES

**Entity Mapper**

The `ElasticsearchEntityMapper` can use metadata to drive the mapping of objects to documents.

For detail we can check [this doco](https://docs.spring.io/spring-data/elasticsearch/docs/current/reference/html/#elasticsearch.mapping.meta-model).


**Query Method**

- paging and sorting

- page and slice: page will know total elements and total page, while slice only knows about whether next slice available.

**Customized Repositories**

Base on the CrudRepository or PagingAndSortingRepository, we can use fragment interface to define the customised repo, in the repo we can use template to query ES to fulfill our special requirement (must have, should have etc.)

**Elasticsearch Template**
TBC



[Reference](https://docs.spring.io/spring-data/elasticsearch/docs/current/reference/html/#repositories.core-concepts)
