---
layout: default
title: Shell
nav_order: 5
---

# Shell
{: .no_toc }

Random tips on shell usage.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Running within a subshell

Sometimes it might prove useful to run a program within a subshell. A particular frequent use case involves trying different JDKs while at the same time not wanting to set a new `JAVA_HOME`. For those cases, a subshell comes to the rescue:

```bash
(JAVA_HOME=/Volumes/DevTools/Java/jdk17/Contents/Home;mvn clean verify)
```

## MD5 hash

In order to quickly get the MD5 hash of any given string, within the terminal:

```bash
md5 <<< "string to test"
```

## Create a new directory and navigate to it one liner

Create a new directory and change to it with this line:

```bash
mkdir <dirName> && cd $_
```