# Docker Compose Guide

## Introduction

Docker Compose is used to define and manage multiple Docker containers as a single application. Instead of manually creating and configuring each container, the required services can be described in a YAML configuration file.

For this laboratory, Docker Compose is used to deploy a Nextcloud application container and a MariaDB database container.

## The `services:` Block

The `services:` block defines the containers that make up the application.

The deployment contains two services:

```yaml
services:

  database:
    ...

  app:
    ...
