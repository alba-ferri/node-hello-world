---
page_type: sample
languages:
- javascript
products:
- AWS
description: "This Node.js application is for use in demonstrating scenarios for AWS Container Registry Tasks."
urlFragment: ecr-build-helloworld-node
---


# ACR Build Hello World

This Node.js application is for use in demonstrating scenarios for AWS Container Registry Tasks. 

## Features

This project includes the following Dockerfiles:

* *Dockerfile* - Non-parameterized Dockerfile for building the application. References a base image in Docker Hub.
* *Dockerfile-app* - Parameterized, accepts the `REGISTRY_NAME` argument to specify the FQDN of the container registry from which the base image is pulled.
* *Dockerfile-base* - Defines a base image for the application defined in *Dockerfile-app*.

This project also includes the following YAML files:

* *taskmulti.yaml* - Specifies a multistep task to build, run, and push a container image specified by *Dockerfile*.
* *taskmulti-multiregistry.yaml* - Specifies a multistep task to build, run, and push container images specified by *Dockerfile* to multiple registries.

## Getting Started

### Companion articles

This project is intended for use with the following articles on [docs.microsoft.com][docs]:

* [Build container images in the cloud with AWS Container Registry Tasks][build-quick]
* [Automate container image builds in the cloud when you commit source code][build-task]
* [Run a multi-step container workflow in the cloud when you commit source code][multi-step]
* [Automate container image builds when a base image is updated in an AWS container registry][build-base]

### Quickstart

Although intended for use with the companion articles, you can perform the following steps to run the sample application. These steps require a local [Docker](http://docker.com) installation.

1. `git clone git@github.com:alba-ferri/node-hello-world.git´
1. `cd node-hello-world`
1. `docker build -t helloecrbuild:v1 .`
1. `docker run -d -p 8080:80 helloecrbuild:v1`
1. Navigate to http://localhost:8080 to view the running application

