# Mission 6 Reflection

Writing a `docker-compose.yml` file makes a cloud engineer's job easier because the configuration for multiple containers can be defined in one place. Instead of manually entering separate commands for the Nextcloud application and MariaDB database, Docker Compose can deploy the services together using a single command. It also makes the deployment easier to repeat because the same configuration can be used again.

I learned that YAML indentation is very important because YAML uses spaces to determine the structure of the configuration. If I use a Tab or place something at the wrong indentation level, Docker Compose may not be able to read the file correctly. This can cause an error and prevent the application from being deployed.

The environment variables were important because they provide configuration information to the containers. Variables such as `MYSQL_PASSWORD`, `MYSQL_DATABASE`, and `MYSQL_USER` provide Nextcloud with the database information it needs. The `MYSQL_HOST=database` variable is also important because it tells the Nextcloud container where the MariaDB service is located.

Deploying Nextcloud in only a few minutes showed me how useful containerization and Infrastructure as Code can be. Instead of manually installing and configuring every component, Docker Compose can use a configuration file to create the required services. This makes the deployment process more organized and repeatable.

Since Mission 1, my understanding of Cloud Computing has developed from learning basic cloud concepts to working with actual cloud infrastructure and deployment tools. I now have a better understanding of containers, databases, networking, Docker Compose, Infrastructure as Code, and deployment automation. This mission also showed me that small configuration details can have a major effect on whether a deployment works correctly.
