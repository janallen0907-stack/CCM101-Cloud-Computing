# Mission 2: Build the Cloud Infrastructure Blueprint

## Mission Overview

In this laboratory, I will learn and explore how cloud infrastructure works. I will use a temporary Linux cloud server to check its resources, identify its main components, compare different cloud providers, and document the findings and work completed during the mission.

## CloudNova Technologies

For this mission, I will act as a cloud engineer for CloudNova Technologies. My task is to check and understand the temporary Linux server provided to me before the company starts setting up its actual cloud infrastructure. This will help me organize the information needed for a better cloud infrastructure plan.

## Objectives

The main objectives of this mission are:

- Investigate the temporary Linux cloud server.
- Identify the server's compute, storage, networking, and operating system components.
- Compare AWS, Microsoft Azure, and Google Cloud Platform.
- Create a simple cloud infrastructure architecture for CloudNova Technologies.
- Document the findings and results in GitHub.

## Cloud Infrastructure Components

The main components identified from the Linux server and the proposed cloud architecture are:

### Compute

The temporary server uses an Intel Xeon E312xx processor with 1 CPU and 1 core. Compute resources provide the processing power needed to run applications and services.

### Storage

The server has a 20 GB disk, with the main root partition using approximately 19 GB. Storage provides space for the operating system, applications, and data.

### Networking

The server returned the IP addresses `172.30.1.2` and `172.17.0.1`. Networking allows the server and other cloud resources to communicate with each other.

### Operating System

The server is running Ubuntu 24.04.4 LTS with the Linux kernel version `6.8.0-136-generic`.

## Tools Used

The following tools were used during this laboratory:

- GitHub
- KillerCoda
- Ubuntu 24.04
- Linux Terminal
- Markdown
- Cloud architecture diagramming tool

## Linux Commands Executed

The following Linux commands were used to investigate the temporary server:

```bash
cat /etc/os-release
uname -r
lscpu
free -h
lsblk
df -h
findmnt
hostname
hostname -I
