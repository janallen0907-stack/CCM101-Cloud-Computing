# MinIO Deployment

## Overview

MinIO was deployed as an S3-compatible object storage server using Docker. The deployment used Docker port mappings and environment variables to configure the MinIO administrator credentials.

## Docker Deployment Command

The following Docker command was provided for the MinIO deployment:

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
-e "MINIO_ROOT_USER=cloudadmin" \
-e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
minio/minio server /data --console-address ":9001"
