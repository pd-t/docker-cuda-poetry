# Docker-CUDA-Poetry: A Comprehensive Guide

Welcome to the Docker-CUDA-Poetry repository! This repository is designed as a foundational base for creating containers that integrate Poetry with CUDA support. It is published on Docker Hub for easy access and deployment. This guide provides an overview of the repository, detailed instructions for usage, and additional tips for optimizing your development experience.

## Repository Overview

The Docker-CUDA-Poetry image is hosted on Docker Hub under the tag 'thomasfraunholz/docker-cuda-poetry'. This repository serves as an essential tool for developers seeking to leverage the power of Poetry in combination with CUDA capabilities within a Docker container.

### Image Tags

The image tags follow the format `thomasfraunholz/docker-cuda-poetry:<poetry_version>+<cuda_version>`. For example, `thomasfraunholz/docker-cuda-poetry:1.6.1+117` indicates that the container uses Poetry version 1.6.1 and CUDA version 117. This naming convention is designed to provide clarity and ease in selecting the appropriate version for your needs.

### Devcontainer Features

The repository includes a development container (devcontainer) with Docker-in-Docker support. This feature allows you to run Docker commands inside your container, providing a more flexible and isolated development environment. Additionally, the devcontainer is configured to automatically pass local SSH keys and gitconfig settings into the container. This integration streamlines the setup process and enhances the convenience of local development.

## Getting Started


Specify the base image from Docker Hub
```Dockerfile
FROM thomasfraunholz/docker-cuda-poetry:<tag>
```

Replace <tag> with the specific version you need, for example, '1.6.1+117'.

Additional Steps: Here you can add any configurations, installations, or setups that are specific to your application. For example, copy your application's source code into the container
```Dockerfile
COPY . /app
WORKDIR /app
```
Install any dependencies (if your project uses a `pyproject.toml` file)
```Dockerfile
RUN poetry install
```
Your application's specific commands can follow...

```Dockerfile
CMD [ "python", "./your-daemon-or-script.py" ]
```
...or any other commands you need to set up your environment.
