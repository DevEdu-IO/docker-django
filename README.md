This repository contains the Dockerfile for a browser-based code IDE (code-server) on Ubuntu, with Python/Django tooling and the **DevEdu Code** AI assistant pre-installed and enabled.

Published to Docker Hub as a **multi-arch** image (`amd64` + `arm64`), so it runs on Intel/AMD and Apple Silicon / ARM machines. Build it yourself with `./build.sh --push` (docker buildx).

# Step 1: Docker Installation

## Windows

### Windows Pro / Education Editions

    https://docs.docker.com/docker-for-windows/install/

### Windows Home

    https://docs.docker.com/docker-for-windows/install-windows-home/

## MacOS

    https://docs.docker.com/docker-for-mac/install/

## Linux

### CentOS

    https://docs.docker.com/install/linux/docker-ce/centos/

### Debian

    https://docs.docker.com/install/linux/docker-ce/debian/

### Fedora

    https://docs.docker.com/install/linux/docker-ce/fedora/

### Ubuntu

    https://docs.docker.com/install/linux/docker-ce/ubuntu/

### Binaries

    https://docs.docker.com/install/linux/docker-ce/binaries/

# Step 2: Pull Image

Download automated build from public Docker Hub Registry:

    docker pull deveduio/django:latest

# Step 3: Running

    docker run -d -p 80:80 -p 3000:3000 deveduio/django:latest

## Step 3: Volume Mount (optional)

You can mount a directory as a volume with the argument \*-v /your-path/directory/:/root/ like this:

    docker run -d -p 80:80 -p 3000:3000 -v /your-path/local/working/directory/:/root/environment deveduio/django:latest

# Step 4: Accessing the Development Environment

## Windows, MacOS, & Linux

    http://localhost/

# Step 5: Django Usage

You can now clone a django repo or create a new application using the development [environment's terminal](https://code.visualstudio.com/docs/terminal/basics):

    mkdir new_repo (or clone from GitHub)
    cd new_repo
    python -m venv myenv --system-site-packages
    source myenv/bin/activate
    django-admin startproject myproject

![terminal](https://github.com/user-attachments/assets/d922d62e-7d10-4b32-9a95-f2cf52a3953f)

# Step 6: Running the Django Application

After creating the new application cd into the directory and run the server:

    cd myproject

and run:

    python manage.py runserver 0.0.0.0:3000

# Step 7: Accessing The Rails Application

## Windows, MacOS, & Linux

    http://localhost:3000

