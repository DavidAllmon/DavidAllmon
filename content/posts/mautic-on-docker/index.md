---
title: Mautic on Docker
subtitle:
date: 2024-04-11T13:05:28Z
slug: f4e7095
draft: false
author:
  name: David Allmon
  link: https://techitdave.com
  email: admin@davidallmon.dev
  avatar: /images/me.png
description:
keywords:
license:
comment: true
weight: 0
tags:
  - Docker
  - Marketing
categories:
  - Docker
  - Marketing
hiddenFromHomePage: false
hiddenFromSearch: false
hiddenFromRss: false
hiddenFromRelated: false
summary:
resources:
  - name: featured-image
    src: mautic-on-docker.png
  - name: featured-image-preview
    src: mautic-on-dockerp.png
toc: true
math: false
lightgallery: false
password:
message:
repost:
  enable: true
  url:

# See details front matter: https://fixit.lruihao.cn/documentation/content-management/introduction/#front-matter
---

# Setting Up Mautic with Docker on Ubuntu 22.04

In this tutorial, we'll walk through the steps to set up Mautic, an open-source marketing automation platform, using Docker on Ubuntu 22.04. Docker simplifies the process of deploying applications by encapsulating them in containers, making it easy to manage dependencies and configurations.

## Prerequisites

Before we begin, ensure you have the following prerequisites installed:
- Docker

## Step 1: Clone Docker-Mautic Repository

First, let's clone the Docker-Mautic repository from GitHub. Navigate to [Docker-Mautic repository](https://github.com/mautic/docker-mautic/tree/mautic5/examples/basic) and clone it to your local system.

`git clone https://github.com/mautic/docker-mautic.git`


## Step 2: Configure Environment

Inside the cloned directory, you'll find three files. Create a new folder for your Mautic instance and copy these three files into the new folder.

`mkdir my-mautic
cp docker-compose.yml .env mautic.env my-mautic/
cd my-mautic`

Now, let's edit the `.env` file to set up the MySQL root password and make some adjustments.

`nano .env`

Find the line `MYSQL_ROOT_PASSWORD=changeme` and replace `changeme` with your desired password.

Additionally, comment out the following lines by adding a `#` at the beginning:

    #DOCKER_MAUTIC_RUN_MIGRATIONS=false
    #DOCKER_MAUTIC_LOAD_TEST_DATA=false


Save the changes and exit the editor.

## Step 3: Run Docker Compose

Now, we're ready to spin up the Mautic container using Docker Compose. Run the following command in your terminal:

`docker-compose up -d`


This command will pull the necessary Docker images and start the Mautic container in detached mode.

## Step 4: Access Mautic

Once the container is up and running, you can access Mautic by visiting `localhost:8001` or  `192.168.0.210:8001` (Whatever your IP is) in your web browser.

## Step 5: Create Admin Account

Upon visiting `localhost:8001` or `192.168.0.210:8001`, you'll be prompted to set up your Mautic instance. Follow the on-screen instructions to create an admin account and complete the setup process.

Congratulations! You have successfully set up Mautic using Docker on your Ubuntu 22.04 system. You can now start leveraging Mautic's powerful marketing automation features for your projects.
