# MinIO Deployment

## Overview

MinIO is an S3-compatible object storage server. In this laboratory activity, MinIO is deployed using Docker to create a proof-of-concept object storage environment for the client's photo-sharing application.

## Docker Deployment Command

The following Docker command is used to deploy the MinIO server:

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
-e "MINIO_ROOT_USER=cloudadmin" \
-e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
minio/minio server /data --console-address ":9001"
