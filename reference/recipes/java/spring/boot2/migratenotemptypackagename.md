# Use NotEmpty

 **org.openrewrite.java.spring.boot2.MigrateNotEmptyPackageName** _`org.hibernate.validator.constraints.NotEmpty` was deprecated in 1.x._

## Source

[Github](https://github.com/openrewrite/rewrite-spring), [Issue Tracker](https://github.com/openrewrite/rewrite-spring/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-spring/4.9.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-spring
* version: 4.9.0

## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-spring:4.9.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.7.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.spring.boot2.MigrateNotEmptyPackageName")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-spring:4.9.0")
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
        <version>4.9.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.spring.boot2.MigrateNotEmptyPackageName</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-spring</artifactId>
            <version>4.9.0</version>
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

Recipes can also be activated directly from the command line by adding the argument `-DactiveRecipe=org.openrewrite.java.spring.boot2.MigrateNotEmptyPackageName`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Change type](../../changetype.md)
  * oldFullyQualifiedTypeName: `org.hibernate.validator.constraints.NotEmpty`
  * newFullyQualifiedTypeName: `javax.validation.constraints.NotEmpty`
* [Add Maven dependency](../../../maven/adddependency.md)
  * groupId: `javax.validation`
  * artifactId: `validation-api`
  * version: `2.x`
  * releasesOnly: `false`
  * onlyIfUsing: `[javax.validation.constraints.NotBlank, javax.validation.constraints.NotEmpty]`
{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.spring.boot2.MigrateNotEmptyPackageName
displayName: Use `NotEmpty`
description: `org.hibernate.validator.constraints.NotEmpty` was deprecated in 1.x.
recipeList:
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: org.hibernate.validator.constraints.NotEmpty
      newFullyQualifiedTypeName: javax.validation.constraints.NotEmpty
  - org.openrewrite.maven.AddDependency:
      groupId: javax.validation
      artifactId: validation-api
      version: 2.x
      releasesOnly: false
      onlyIfUsing: [javax.validation.constraints.NotBlank, javax.validation.constraints.NotEmpty]
```
{% endtab %}
{% endtabs %}
