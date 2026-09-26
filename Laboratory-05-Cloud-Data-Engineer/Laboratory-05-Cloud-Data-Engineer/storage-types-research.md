# Cloud Storage Types Research

Cloud storage can be categorized into three primary types: Block Storage, File Storage, and Object Storage. Each type organizes and accesses data differently and is suited to different workloads.

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| Block Storage | Stores data as individual blocks that can be attached to a virtual machine or server as storage volumes. | Operating system disks, databases, and applications that require low-latency storage. | AWS EBS |
| File Storage | Stores data in a hierarchical file and folder structure that can be accessed by multiple systems over a network. | Shared files, documents, application files, and workloads requiring shared file access. | AWS EFS |
| Object Storage | Stores data as objects together with metadata and unique identifiers inside containers called buckets. | Large amounts of unstructured data such as images, videos, backups, and other media files. | Amazon S3 |

## Why Object Storage is Suitable for the Client

Object Storage is well suited for the client's photo-sharing application because images are unstructured files that can be stored as individual objects and accessed through a scalable storage system. It is designed for storing large amounts of data such as images and backups, making it appropriate for an application that may receive millions of user-uploaded photos.
