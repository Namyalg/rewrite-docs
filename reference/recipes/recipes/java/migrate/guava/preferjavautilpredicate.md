# Prefer `java.util.function.Predicate`

** org.openrewrite.java.migrate.guava.PreferJavaUtilPredicate**
_Guava's `Predicate` extends `java.util.function.Predicate`._

### Tags

* guava, RSPEC-4738

## Source

[Github](https://github.com/openrewrite/rewrite-migrate-java), [Issue Tracker](https://github.com/openrewrite/rewrite-migrate-java/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-migrate-java/1.4.3/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-migrate-java
* version: 1.4.3


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-migrate-java:1.4.3 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.19.2")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.guava.PreferJavaUtilPredicate")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:1.4.3")
}
```
{% endcode %}
{% endtab %}

{% tab title="Maven" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.22.2</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.guava.PreferJavaUtilPredicate</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>1.4.3</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-DactiveRecipe=org.openrewrite.java.migrate.guava.PreferJavaUtilPredicate`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `com.google.common.base.Predicate`
  * newFullyQualifiedTypeName: `java.util.function.Predicate`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.guava.PreferJavaUtilPredicate
displayName: Prefer `java.util.function.Predicate`
description: Guava's `Predicate` extends `java.util.function.Predicate`.
tags:
  - guava, RSPEC-4738
recipeList:
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: com.google.common.base.Predicate
      newFullyQualifiedTypeName: java.util.function.Predicate

```
{% endtab %}
{% endtabs %}