# Mission 5 Reflection

At the start of this activity, I did not really understand what MinIO was. I knew it was related to cloud storage, but I did not know how it was different from normal storage on a computer. After doing the activity, I understood that Object Storage is useful for applications that need to store a large number of files such as photos. Instead of treating the files like normal folders and hard drives, the files are stored as objects inside buckets, which makes it more suitable for a photo-sharing application.

Using Docker also made more sense to me after actually doing it. At first, I thought I could simply use the command provided in the laboratory, but I encountered problems because the original MinIO Docker image was no longer available from Docker Hub. Instead of stopping there, I built a local MinIO Docker image from the source code and was able to run it successfully. This also helped me understand that Docker can package an application and its environment so that it can be run without manually installing everything on the computer.

A bucket is basically a container for objects in Object Storage. In this activity, I created a bucket called `client-photos` and uploaded a screenshot into it. Seeing the file appear in the MinIO Web Console made the concept easier to understand compared to only reading about it.

For large companies, I think protecting object storage would require redundancy, replication, and backups so that data is not dependent on one physical server. If one server fails, another copy can still be available.

This activity also made me more comfortable with command-line tools. I had several errors during the deployment, but troubleshooting them helped me understand Docker commands such as `docker build`, `docker run`, `docker images`, and `docker ps` instead of just copying commands without knowing what they did.
