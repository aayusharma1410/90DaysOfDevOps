
Day 31 – Dockerfile: Build Your Own Images

Objective

The objective of this task was to understand how Docker images are built using Dockerfiles. Instead of only running containers, I focused on writing Dockerfiles from scratch, building custom images, understanding layer caching, and optimizing builds.

------------------------------------------------------------

Task 1 – My First Dockerfile

Dockerfile:

FROM ubuntu:latest
RUN apt-get update && apt-get install -y curl
CMD ["echo", "Hello from my custom image!"]

Build Command:
docker build -t my-ubuntu:v1 .

Run Command:
docker run my-ubuntu:v1

Result:
The container successfully printed:
Hello from my custom image!

------------------------------------------------------------

Task 2 – Using All Dockerfile Instructions

Dockerfile:

FROM ubuntu:latest
RUN apt-get update && apt-get install -y curl
WORKDIR /app
COPY app.txt .
EXPOSE 8080
CMD ["cat", "app.txt"]

Explanation:
FROM sets the base image.
RUN executes commands during image build.
WORKDIR sets the working directory inside the container.
COPY copies files from the host to the image.
EXPOSE documents the port used by the container.
CMD defines the default command when the container starts.

------------------------------------------------------------

Task 3 – CMD vs ENTRYPOINT

CMD Example:

FROM ubuntu
CMD ["echo", "hello"]

Running:
docker run cmd-image
Output: hello

Running:
docker run cmd-image ls
CMD can be overridden by passing another command.

ENTRYPOINT Example:

FROM ubuntu
ENTRYPOINT ["echo"]

Running:
docker run entry-image hello
Output: hello

Running:
docker run entry-image ls
Output: ls

ENTRYPOINT always runs and appends additional arguments.

Conclusion:
CMD is used for default commands that can be overridden.
ENTRYPOINT is used when a container must always run a specific executable.

------------------------------------------------------------

Task 4 – Deploying a Simple Web App

Dockerfile:

FROM nginx:alpine
COPY index.html /usr/share/nginx/html/

Build Command:
docker build -t my-website:v1 .

Run Command:
docker run -d -p 8080:80 my-website:v1

Access:
http://localhost:8080

The web page loaded successfully, confirming that Nginx was serving the static content from inside the container.

------------------------------------------------------------

Task 5 – Using .dockerignore

.dockerignore Content:

node_modules
.git
*.md
.env

This reduces build time and prevents unnecessary files from being included in the Docker image.

------------------------------------------------------------

Task 6 – Build Optimization and Layer Caching

Observations:

Docker builds images layer by layer.
If a layer changes, all layers after it are rebuilt.
Layer order directly affects build speed.
Frequently changing files should be copied at the end of the Dockerfile.

Optimizing layer order improves build performance, especially in CI/CD pipelines.

------------------------------------------------------------

Final Summary

Through this task, I learned how to:
- Write Dockerfiles from scratch
- Build and tag custom Docker images
- Understand Docker layer caching
- Use CMD and ENTRYPOINT appropriately
- Deploy a static website using Nginx
- Optimize Docker builds for better performance

This task helped me move from simply running containers to building structured and optimized Docker images.
