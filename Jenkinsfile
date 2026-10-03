// Release pipeline for this repo: push a release-X.Y.Z tag (X.Y.Z = pom.xml version, tag on main).
// All stages live in the shared library "vdx-pipeline-lib"; this file says only WHAT to release.
@Library('vdx-pipeline-lib') _

javaReleasePipeline(
    // Required
    imageName:      'docker.io/anujdocker9799/java-maven-sample-app',   // pushed as <imageName>:release-X.Y.Z
    registryCredId: 'dockerhub-anujdocker9799',                 // your Docker Hub credential ID (step 2)
    healthPath:     '/greeting'                                 // smoke test expects a 2xx here
    // Optional: uncomment a line to change it (keep its leading comma); the value shown is the default
    // , appPort:     8080                                      // port the app listens on
    // , ancestryRef: 'main'                                    // branch a release tag must be on
    // , mavenImage:  'docker.io/library/maven:3.9.9-eclipse-temurin-21'   // Maven/JDK image for the build
    // , agentLabel:  'vdx-podman'                              // Jenkins agent that runs the build
)
