// Release pipeline for this repo: push a release-X.Y.Z tag (X.Y.Z = pom.xml version, tag on main).
// All stages live in the shared library "vdx-pipeline-lib"; this file says only WHAT to release.
@Library('vdx-pipeline-lib') _

javaReleasePipeline(
    imageName:      'docker.io/anujdocker9799/compvalidator',   // pushed as <imageName>:release-X.Y.Z
    registryCredId: 'dockerhub-anujdocker9799',          // your Docker Hub credential ID (step 2)
    healthPath:     '/greeting'                               // smoke test expects a 2xx here
)