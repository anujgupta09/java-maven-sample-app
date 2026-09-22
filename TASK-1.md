# Task 1: Application Input

The application is Spring's small REST-service sample. See [UPSTREAM.md](UPSTREAM.md)
for its pinned source, licence and modifications. The packaging pipeline is the
assessment deliverable; the reused application provides a simple build input.

- Application version: `1.0.0`, corresponding to the planned release tag `release-1.0.0`.
- Java source target: `17`; Spring Boot parent: `4.0.8`. These are separate from
  the application version used in the release tag.
- `GET /greeting` returns JSON containing an `id` and `content: "Hello, World!"`.
- `GET /greeting?name=Anuj` returns `content: "Hello, Anuj!"`.
- Two upstream tests cover default and named greetings. No database is required.

## Container-Only Build

Prerequisites: a running Linux-container engine (Docker or Podman), access to
pull the build image and Maven dependencies, and permission to mount this
working directory. Do not install Java or Maven on the host for this build.

Build toolchain: Maven `3.9.9` with Eclipse Temurin JDK `17`, using
`docker.io/library/maven:3.9.9-eclipse-temurin-17`. JDK 17 matches the sample's
Java target.

From this repository's root (the directory containing `pom.xml`), run in Bash:

```bash
project_dir="$(pwd -W 2>/dev/null || pwd)"
podman run --rm \
  -v "${project_dir}:/workspace" \
  -v vdx-task1-maven-cache:/root/.m2 \
  --workdir /workspace \
  docker.io/library/maven:3.9.9-eclipse-temurin-17 \
  mvn -B clean verify
```

Substitute `docker` for `podman` if using Docker. The bind mount makes the
checkout available in the container; the named volume caches Maven
dependencies across runs. If the checkout path contains characters such as a
comma, prefer `-v` over `--mount`, which can misparse such paths.

After a successful build, the expected executable JAR is
`target/rest-service-complete-1.0.0.jar`, with test reports under
`target/surefire-reports/`. This Maven image is only a build environment, not the
final Debian 13 runtime image.

## Current Verification Status

This build has been run successfully in a container, compiling the application
and passing both upstream tests (default and named greetings). The Debian 13
runtime image and Jenkins pipeline are not implemented yet. No release tag or
image has been published.