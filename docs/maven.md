---
layout: default
title: Maven
nav_order: 6
---

# Maven
{: .no_toc }

Random tips regarding maven.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Test javadoc generation locally

Because waiting for Jenkins to notify you about a wrongly formed javadoc is not cool. Issue this command and if no errors are shown, you're good to go:

```shell
mvn javadoc:javadoc | grep -i ": error:"
```

## Filtering using resources

Adding this to your `pom.xml` will replace all placeholders within files in the the `src/main/resources` folder with properties available while running the `process-resources` phase.

```xml
<resource>
  <directory>src/main/resources</directory>
  <filtering>true</filtering>
</resource>
```
