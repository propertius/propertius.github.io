---
layout: default
title: Java
nav_order: 2
---

# Java
{: .no_toc }

Random tips regarding Java development.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Locale problems after JDK 8

If the project uses different locales, it is possible that your production or test environment show unexpected formatting on numbers. This is because newer versions of the JDK prefer using the Common Locale Data Repository ([CLDR](https://cldr.unicode.org/)). In order to get JDK behavior set the following flag:

```java
-Djava.locale.providers=COMPAT
```

## Prefer records over classes for immutable objects

One big advantage of records over regular classes is the out-of-the-box `equals` and `hashCode` implementations you get. When using records, the `equals` methods is used for references and primitives (through wrappers), applied to all components. Compare that to a regular class, which only compare references (`==`).

## Use java.nio.charset.StandardCharsets

Pretty much all variants of any IO API will ask for a java.nio.Charset as a Parameter. And in most cases, you'll want to use UTF-8. For those cases, prefer this form:
```java
import java.nio.charset.StandardCharsets;
//...
IOUtils.readLines(inputStream, StandardCharsets.UTF_8)...
```
over this one:
```java
import java.nio.charset.Charset;
//...
IOUtils.readLines(inputStream, Charset.forName("UTF-8"))...
```
