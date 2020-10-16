---
description: Install SuperCoreAPI to create plugins
---

# Installation

## Maven

First, you need to add the repository for the plugin, if you already have the repo skip this step

```markup
<!-- SuperCoreAPI -->
<repository>
    <id>TheProgramSrc</id>
    <url>https://repo.theprogramsrc.xyz/repository/maven-public</url>
</repository>
```

Now, you need to add the dependency

```markup
<!-- SuperCoreAPI -->
<dependency>
    <groupId>xyz.theprogramsrc</groupId>
    <artifactId>SuperCoreAPI</artifactId>
    <version>{LAST VERSION}</version>
</dependency>
```

Latest SuperCoreAPI Version: [GitHub](https://github.com/TheProgramSrc/SuperCoreAPI/releases/latest). Those settings should be placed in your `pom.xml` file.

{% hint style="warning" %}
If you want to use versions older or equals than the `v2.4.9` you may don't find it because of the migration to our own repository.
{% endhint %}

