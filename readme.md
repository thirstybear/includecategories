# Possible bug in Gradle JUnit Category handling

Simple SpringBoot application, with a simple SpringRunner/SpringBootTest test.

Defined a Category interface `IntegrationTest`, but it is unused.

Added a `integrationtest` Gradle task that only includes the `IntegrationTest` category.

Run using `./gradlew integrationtest --info` and can see that it picks up the _uncategorised_ `ApplicationTest`