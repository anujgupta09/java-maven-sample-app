# Upstream Application Attribution

The demonstration Java application is reused from Spring's official
[Building a RESTful Web Service sample](https://github.com/spring-guides/gs-rest-service),
not original application code developed for this assessment.

- Source commit: `3f4cef01152596c19bc4d37939409358812b1421`.
- Source directory: [`complete`](https://github.com/spring-guides/gs-rest-service/tree/3f4cef01152596c19bc4d37939409358812b1421/complete).
- Imported files: `complete/pom.xml`, all four Java files under `complete/src/`,
  and the upstream root `LICENSE.txt`.
- Layout: the contents of `complete/` are placed at this repository's root.
- Licence: Apache License 2.0; the original text is retained in [LICENSE.txt](LICENSE.txt).
  No separate upstream NOTICE file was present at this commit.
- Excluded: Gradle configuration, Maven/Gradle wrappers, starter and Kotlin
  examples, and guide prose. Compilation will use Maven supplied by a container.

## Modifications

- [pom.xml](pom.xml): changed only the application version from `0.0.1-SNAPSHOT`
  to `1.0.0` and added a modification notice. Spring Boot `4.0.8`, Java target
  `17`, dependencies and packaging configuration are unchanged.
- All imported Java source and test files, and the licence text, are unchanged.
- Repository build instructions, this attribution document and `.gitignore`
  were added for the assessment; they are not copied from the Spring guide.