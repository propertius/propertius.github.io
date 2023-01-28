---
layout: default
title: Server Configuration
nav_order: 3
---

# Server Configuration
{: .no_toc }

Random tips on configuring a server.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Max POST size

By default Wildfly (or JBoss) will limit the maximum allowed size for a `POST` request to 10 MB. You may quickly change that by setting the `max-post-size` property within the `standalone.xml` file.

```xml
# Set the maximum post size to unlimited
<http-listener name="default" max-post-size=„0“ redirect-socket="https" socket-binding="http"/>
```
