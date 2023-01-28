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

