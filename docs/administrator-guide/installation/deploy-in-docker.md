---
layout: post
title: Deployment on Docker compose in Bold Reports Server.
description: In the bold reports enterprise reporting, learn how to set up the deployment on docker compose for the Bold Reports Enterprise Edition.
platform: report-platform
documentation: ug
---

# Deploying in Docker

Bold Reports Docker can run on different Linux distributions.

## Prerequisites

This section explains the requirements to use the Bold Reports on Docker and deploy them using the docker-compose deployment.

### Hardware requirements

The following hardware requirements are necessary to run the Bold Reports solution:

* **Operating System**: Bold Reports Docker can run on different Linux distributions. Verified on the following operating systems:
    * Ubuntu 18.04 LTS
    * Cent OS 7
    * Windows
    * Red Hat Enterprise Linux (RHEL)
    * Alpine Linux
* **CPU**: 4-core.
* **Memory**: 16 GB RAM.
* **Disk Space**: 8 GB or more.

### Software requirements

The following software requirements are necessary to run the Bold Reports Enterprise edition:

* **Database**: Microsoft SQL Server 2012+ | PostgreSQL
* **Application**: Docker
* **Web Browser**: Microsoft Edge, Mozilla Firefox, and Chrome

## Installation

Bold Reports can be deployed using docker-compose. Nginx will run in a separate container as a reverse proxy to route traffic to other containers. Please follow the below link to deploy Bold Reports using the docker-compose deployment.

[Bold Reports on Docker](https://github.com/boldreports/bold-reports-docker)