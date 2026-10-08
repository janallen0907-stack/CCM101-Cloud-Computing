# Mission 6: The Cloud Deployment Engineer

## Mission Overview

Mission 6 focused on deploying a private cloud storage application using Docker Compose.

The application uses a two-tier architecture consisting of:

1. **Nextcloud** - the web/application tier
2. **MariaDB** - the database tier

Instead of creating and configuring each container separately, Docker Compose was used to define the complete application stack in one YAML configuration file.

The deployment was performed locally using Docker Desktop on Windows.

---

## Objectives

The main objectives of this mission were:

- Understand two-tier and multi-container application architecture.
- Understand how Docker Compose defines multiple services.
- Create a Docker Compose configuration file.
- Configure Nextcloud and MariaDB.
- Deploy the application using Docker Compose.
- Access Nextcloud through a web browser.
- Verify that the containers are running correctly.
- Stop and remove the deployment using Docker Compose.
- Document the deployment as Infrastructure as Code.
- Store deployment evidence in the GitHub Cloud Computing portfolio.

---

# 1. Project Architecture

The deployment consists of two main services.

```text
User Browser
     |
     | HTTP :8080
     v
+---------------------------+
| Nextcloud Application     |
| Container                 |
|                           |
| Port 8080 -> 80           |
+-------------+-------------+
              |
              | MySQL/MariaDB
              |
              v
+---------------------------+
| MariaDB Database          |
| Container                 |
|                           |
| Database: nextcloud_db    |
+---------------------------+
```

The browser communicates with the Nextcloud container through port `8080`.

Nextcloud then communicates with the MariaDB container through the Docker Compose network.

This separates the application from the database instead of putting everything inside one container.

---

# 2. Two-Tier Architecture

A two-tier architecture separates an application into two main parts.

### Web/Application Tier

The web/application tier handles user requests and provides the application interface.

In this deployment, **Nextcloud** acts as the web/application tier.

Users access Nextcloud through a web browser.

### Database Tier

The database tier stores the persistent data required by the application.

In this deployment, **MariaDB** acts as the database tier.

The two containers communicate through the Docker Compose network.

The application does not need to connect to the database using the host machine's IP address. Instead, Docker Compose provides service-to-service communication using the service name.

For this deployment:

```text
MYSQL_HOST: database
```

The name `database` refers to the MariaDB service defined in the Compose file.

---

# 3. Docker Compose Configuration

The deployment was defined using a file named:

```text
docker-compose.yml
```

The configuration defines two services:

```yaml
services:
  app:
    ...
    
  database:
    ...
```

The `app` service runs Nextcloud.

The `database` service runs MariaDB.

Docker Compose creates a network for these services so they can communicate with each other.

---

# 4. Nextcloud Application Service

The Nextcloud service uses the Nextcloud Docker image.

Example configuration:

```yaml
app:
  image: nextcloud
  environment:
    MYSQL_DATABASE: nextcloud_db
    MYSQL_HOST: database
    MYSQL_PASSWORD: cloudnova_pass
    MYSQL_USER: nextcloud_user
  ports:
    - "8080:80"
```

The important parts are:

### Image

```yaml
image: nextcloud
```

This tells Docker to use the Nextcloud image.

### Database Host

```yaml
MYSQL_HOST: database
```

This tells Nextcloud that the database is available through the MariaDB service named `database`.

### Database Name

```yaml
MYSQL_DATABASE: nextcloud_db
```

This identifies the database that Nextcloud will use.

### Database User

```yaml
MYSQL_USER: nextcloud_user
```

This defines the database account used by Nextcloud.

### Database Password

```yaml
MYSQL_PASSWORD: cloudnova_pass
```

This provides the password for the Nextcloud database user.

### Port Mapping

```yaml
ports:
  - "8080:80"
```

Port `8080` on the Windows host is connected to port `80` inside the Nextcloud container.

Therefore, Nextcloud can be accessed through:

```text
http://localhost:8080
```

---

# 5. MariaDB Database Service

The database service uses MariaDB.

Example configuration:

```yaml
database:
  image: mariadb:10.6
  environment:
    MYSQL_DATABASE: nextcloud_db
    MYSQL_PASSWORD: cloudnova_pass
    MYSQL_ROOT_PASSWORD: cloudnova_root
    MYSQL_USER: nextcloud_user
```

The important configuration values are:

```text
Database: nextcloud_db
User: nextcloud_user
Password: cloudnova_pass
Root Password: cloudnova_root
```

The MariaDB container provides the database required by Nextcloud.

The database is not exposed to the browser. It is used internally by the application container.

---

# 6. Docker Network

Docker Compose automatically creates a network for the services.

The network created for this project was:

```text
nextcloud-deployment_default
```

Both the Nextcloud and MariaDB containers are connected to this network.

This allows the application to communicate with the database using:

```text
database
```

instead of using a hard-coded IP address.

The Docker network is important because the application and database need to communicate while remaining separate containers.

---

# 7. Validating the Configuration

Before starting the deployment, the Compose configuration was checked using:

```powershell
docker compose config
```

This command parses the YAML configuration and displays the resolved Compose configuration.

The configuration was successfully recognized by Docker Compose.

There was a warning that the `version` attribute is obsolete in the current Docker Compose implementation. This warning does not prevent the deployment from running.

---

# 8. Deploying the Application

The application was started using:

```powershell
docker compose up -d
```

The `-d` option runs the containers in detached mode, allowing the PowerShell terminal to remain available.

During deployment, Docker:

1. Pulled the required images.
2. Created the Docker network.
3. Created the MariaDB container.
4. Created the Nextcloud container.
5. Started both containers.

The deployment completed successfully.

---

# 9. Checking the Running Containers

The running containers were checked using:

```powershell
docker compose ps
```

The result showed two running services:

```text
nextcloud-deployment-app-1
nextcloud-deployment-database-1
```

Both containers had an `Up` status.

The Nextcloud container also showed the port mapping:

```text
0.0.0.0:8080->80/tcp
```

This confirms that the Nextcloud web application was running and available through port `8080`.

The deployment screenshot is stored as:

```text
screenshots/compose-deployment.png
```

---

# 10. Accessing Nextcloud

After the containers were running, Nextcloud was opened through a web browser using:

```text
http://localhost:8080
```

The Nextcloud installation page appeared.

The page detected the configuration values provided by the Docker setup and displayed:

```text
Autoconfig file detected
```

This confirmed that the Nextcloud container was running correctly and that its configuration was being recognized.

The browser screenshot is stored as:

```text
screenshots/nextcloud-web.png
```

---

# 11. Administration Account

The Nextcloud setup page provided the option to create an administration account.

The administrator account is separate from the MariaDB database account.

The database credentials are used by Nextcloud to communicate with MariaDB, while the administration account is used to log in to the Nextcloud application.

This separation allows the application and database credentials to serve different purposes.

---

# 12. Stopping the Deployment

After testing the deployment, the Docker Compose application was stopped and removed using:

```powershell
docker compose down
```

This command removes the containers and the Docker Compose network created for the deployment.

The teardown result showed that:

```text
Container nextcloud-deployment-database-1 Removed
Container nextcloud-deployment-app-1 Removed
Network nextcloud-deployment_default Removed
```

This confirms that the Compose deployment could be removed as a single application stack.

The teardown evidence is stored as:

```text
screenshots/compose-teardown.png
```

---

# 13. Infrastructure as Code

Docker Compose is useful because the infrastructure can be described using a configuration file instead of manually creating every container.

The `docker-compose.yml` file defines:

- Application services
- Database services
- Container images
- Environment variables
- Port mappings
- Network configuration

Because the configuration is stored as a file, the deployment can be recreated using the same configuration.

This is an example of the Infrastructure as Code approach.

---

# 14. Deployment Evidence

The following screenshots were included in this repository:

| Screenshot | Purpose |
|---|---|
| `compose-deployment.png` | Shows the Docker Compose deployment and both containers running |
| `nextcloud-web.png` | Shows the Nextcloud web interface and detected configuration |
| `compose-teardown.png` | Shows the containers and network being removed |

These files provide visual evidence of the main deployment stages.

---

# 15. Summary

Mission 6 demonstrated how a multi-container application can be deployed locally using Docker Compose.

The final architecture consisted of:

```text
Browser
   |
   | localhost:8080
   v
Nextcloud
   |
   | Docker Network
   v
MariaDB
```

The main process was:

```text
Create docker-compose.yml
        ↓
docker compose config
        ↓
docker compose up -d
        ↓
docker compose ps
        ↓
Open http://localhost:8080
        ↓
Verify Nextcloud
        ↓
docker compose down
```

The deployment was successfully created, tested, and removed using Docker Compose.

The configuration and screenshots were then documented in the GitHub Cloud Computing portfolio.
