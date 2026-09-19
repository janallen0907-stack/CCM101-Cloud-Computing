# Mission 4: The Cloud-Native Engineer

## Mission Overview

This laboratory introduces cloud-native engineering through the use of containerization and Docker. The activity focuses on understanding the differences between traditional Virtual Machines (VMs) and containers, using a Docker-enabled Linux environment, deploying an Nginx web server, and managing the lifecycle of a container.

The practical demonstration was performed using the KillerCoda Playground. The Docker command-line interface was used to verify the environment, download an Nginx image, run the web server, test its availability, and manage the container.

## Objectives

- Differentiate between Virtual Machines and containers.
- Access a Docker-enabled Linux cloud environment.
- Verify that Docker is installed and operational.
- Pull and run the official Nginx container image.
- Map a host network port to a container port.
- Test a containerized web server using `curl`.
- Manage the lifecycle of a Docker container.
- Document cloud-native operations using Markdown.
- Maintain an organized GitHub Cloud Computing portfolio.

## Docker Commands Executed

### Docker Environment Verification

```bash
docker --version
docker info
