# Jenkins

## Installation

- `java -jar jenkins.war --httpPort=8080`.
- Browse to http://localhost:8080
- Follow the instructions to complete the installation.
  - Select Standard Plugins and Complete installation

## PipeLine

- Jenkins Pipeline (or simply "Pipeline") `is a suite of plugins` which `supports implementing and integrating continuous delivery pipelines` into Jenkins.
- Pipelines are made up of multiple steps that allow you to build, test and deploy applications. __When a step succeeds it moves onto the next step.__

## Plugins

- Install Standard Recommended Plugins.
- Maven Info Plugin.
- Extended Choice Parameter - Useful for parameterizing the build.
- [Git Parameter Plugin](https://wiki.jenkins.io/display/JENKINS/Git+Parameter+Plugin) - Adds ability to choose branches, tags or revisions from git repository.
  
# Docker

- Install `docker.dmg` and launch docker deamon
- Docker has prebuilt images for maven, java and other commonly used images readily available
- Checkout [Docker Get Started](https://docs.docker.com/get-started/)
