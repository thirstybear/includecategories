# *NOT* a bug in Gradle JUnit Category handling

Simple SpringBoot application, with a simple SpringRunner/SpringBootTest test.

Defined a Category interface `IntegrationTest`, but it is unused.

Added a `integrationtest` Gradle task that only includes the `IntegrationTest` category.

Run using `./gradlew integrationtest --info` and can see that it picks up the _uncategorised_ `ApplicationTest`

## What is happening?

The tests are not being run, but the SpringRunner(?) annotation is causing a `TestContext` to be created. 
Shouldn't be an issue though?

Some (limited) further info [here](https://stackoverflow.com/questions/49316077/junit-category-annotation-with-springrunner-class)