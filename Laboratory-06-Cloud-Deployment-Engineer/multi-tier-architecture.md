# Multi-Tier Architecture

## What is a Two-Tier Architecture?

A two-tier architecture separates an application into two main tiers: the web/application tier and the database tier. The web/application tier handles user requests and application functions, while the database tier stores the persistent data required by the application.

In this laboratory, the two tiers are represented by a Nextcloud application container and a MariaDB database container.

## The Web/Application Tier

The web/application tier is responsible for serving the user interface and handling HTTP requests from users.

For this deployment, Nextcloud acts as the web/application tier. Users access Nextcloud through a web browser, and the application handles requests related to the private cloud storage system.

The Nextcloud container is exposed through port `8080`, which is mapped to port `80` inside the container.

The relevant Docker Compose configuration is:

```yaml
app:
  image: nextcloud
  ports:
    - 8080:80
