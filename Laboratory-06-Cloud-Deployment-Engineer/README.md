# Mission 6: The Cloud Deployment Engineer

## Mission Overview

Mission 6 focused on deploying a multi-container private cloud storage application using Docker Compose. The application uses a two-tier architecture consisting of a Nextcloud web/application container and a MariaDB database container.

Instead of deploying each container manually, Docker Compose was used to define the infrastructure in a YAML configuration file. This allowed the entire application stack to be deployed and managed using a single configuration.

## Objectives

- Explain the concept of a two-tier and multi-container application architecture.
- Understand the purpose and structure of a `docker-compose.yml` file.
- Use the Linux command-line text editor `nano` to create a configuration file.
- Deploy a multi-container application consisting of Nextcloud and MariaDB.
- Access the Nextcloud web interface through a browser.
- Document Docker Compose and Infrastructure as Code concepts using Markdown.
- Maintain deployment evidence and documentation in a GitHub Cloud Computing portfolio.

## Project Architecture

The deployment consists of two main services:

```text
User Browser
     |
     | HTTP
     v
Nextcloud Application
     |
     | MySQL/MariaDB Connection
     v
MariaDB Database
