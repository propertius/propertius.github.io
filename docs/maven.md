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

## Display available plugin updates

Show available plugin updates within your project by running:

```shell
mvn versions:display-plugin-updates
```

## Display available dependency updates

Show available dependency updates within your project by running:

```shell
mvn versions:display-dependency-updates
```

## Clean local copy of NVD CVE data

Sometimes you need to force the dependency analyzer to clean the local copy hosting NVD data.

```shell
mvn org.owasp:dependency-check-maven:purge
```
## Download sources for a specific JAR with Maven

No need to wait for Maven to download all the sources for all dependencies within your project. With these command, only the sources of the specified artefact will be downloaded:

```shell
mvn dependency:sources -DincludeGroupIds=some-group -DincludeArtifactIds=some-artifact-id
```

