# java-maven-sample-app

A small Spring Boot REST service used as the build input for a Jenkins/Podman
packaging pipeline assessment. This repository holds only the Java
application; the Jenkins pipeline, Docker/Podman build tooling and the
Debian 13 runtime image recipe live in a separate assessment repository.

## What this is

`GET /greeting` returns a JSON greeting (`Hello, World!`, or `Hello, <name>!`
with `?name=`). Two tests cover both cases. There is no database or external
service dependency.

## Where it's from and why

Reused as-is from Spring's official sample, [Building a RESTful Web
Service](https://github.com/spring-guides/gs-rest-service), pinned to commit
[`3f4cef0`](https://github.com/spring-guides/gs-rest-service/tree/3f4cef01152596c19bc4d37939409358812b1421/complete),
rather than written from scratch — the assessment is evaluating the CI/CD
packaging pipeline, not application development, so a small, well-understood,
dependency-free sample keeps that the focus. See [UPSTREAM.md](UPSTREAM.md)
for the exact imported files and the two intentional modifications (version
bump to `1.0.0` and a build-instructions/attribution addition); everything
else, including the licence, is unchanged.

## Licence

Apache License 2.0, unchanged from upstream. See [LICENSE.txt](LICENSE.txt).

## Building

See [TASK-1.md](TASK-1.md) for the container-only build command and current
verification status.
