This repository contains Dockerfile of code IDE running on Ubuntu for Docker's automated build published to the public Docker Hub Registry.
### Note: This will only work on AMD64 devices. ARM will need to be downloaded and built on the user's computer.

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

    http://localhost/?folder=/root

# Step 5: Django Usage

You can now clone a django repo or create a new application using the code terminal:

    python -m venv myenv
    source myenv/bin/activate
    django-admin startproject myproject

# Step 6: Running the Django Application

After creating the new application cd into the directory and run the server:

    cd myproject

and run:

    python manage.py runserver 0.0.0.0:3000

# Step 7: Accessing The Rails Application

## Windows, MacOS, & Linux

    http://localhost:3000

