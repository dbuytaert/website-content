---
url: 'https://dri.es/running-activepieces-locally-with-docker'
title: 'Running Activepieces locally with Docker'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-11-07T04:15:28-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: note
tags:
  - Activepieces
  - Drupal
  - Automation
published: true
featured: false
id: 5921
---

# Running Activepieces locally with Docker

For [Drupal](https://www.drupal.org/) developers, [Activepieces](https://www.activepieces.com/) makes it easy to connect Drupal to other systems. Think of it as an open source alternative to tools like [Zapier](https://zapier.com/) or [n8n](https://n8n.io/), but with an MIT license.  

For example, you can create a workflow that runs when new content is published in [Drupal](https://www.drupal.org/) and automatically sends it to [Slack](https://slack.com/), [Google Sheets](https://www.google.com/sheets/about/), or social media. You can also trigger Drupal actions, such as creating new content or updating user data, when something changes in [Salesforce](https://www.salesforce.com/), [GitHub](https://github.com/), or [Airtable](https://www.airtable.com/).

This guide covers running [Activepieces](https://www.activepieces.com/) locally using [Docker](https://www.docker.com/). This setup is ideal if you're developing Drupal sites locally with [DDEV](https://ddev.com/) and want to build workflows that connect to your local Drupal instance.

When you develop Drupal sites locally, Activepieces Cloud can't reach them. You could use a tunneling service like [ngrok](https://ngrok.com/) to expose your local environment to the internet, but that adds extra complexity.

Instead, we can run an open source copy of Activepieces locally using [Docker](https://www.docker.com/). This gives you a fully configured Activepieces instance that can communicate directly with your local [Drupal](https://www.drupal.org/) site. You can get up and running in just a few minutes with a single command.

### Contributing to the Drupal Piece

In Activepieces, a *Piece* is an integration that connects to an external application or service. I helped build the original [Drupal Piece](https://www.activepieces.com/pieces/drupal), which now ships with Activepieces out of the box. It lets you create workflows that move data between Drupal and other applications.  

If you want to contribute to the Drupal Piece, this Docker setup is _not_ what you need. The Docker instance runs like a production environment. It's perfect for building and testing workflows in Activepieces, but it doesn't let you modify the Activepieces code or the Drupal Piece itself.  

To make changes to Activepieces, including the Drupal Piece, you'll need to [set up a full Activepieces development environment](https://dri.es/setting-up-an-activepieces-development-environment) instead.  

However, if your goal is simply to run Activepieces locally and connect it to your Drupal site, the Docker setup below is all you need.  

### Run Activepieces locally with Docker 

This one-line command will download and run Activepieces on your computer:

```bash
docker run -d -p 8080:80 -v ~/.activepieces:/root/.activepieces -e AP_QUEUE_MODE=MEMORY -e AP_DB_TYPE=SQLITE3 -e AP_FRONTEND_URL="http://localhost:8080" activepieces/activepieces:latest
```

This pulls the latest Activepieces image from Docker Hub (if it isn't already cached) and starts a container with the following settings:

* Runs in detached mode (-d)
* Maps port 8080 on your computer to port 80 in the container
* Persists data by mounting `~/.activepieces` to the container
* Uses in-memory queue processing and SQLite database
* Sets the frontend URL to `http://localhost:8080`

This might take a couple of minutes to boot up the container and get Activepieces up and running. After a couple of minutes, navigate to `http://localhost:8080` (not `https`) to create an account and log into your local instance.

To start using Activepieces with your Drupal site, you still need to connect them. See my guide on [connecting Drupal with Activepieces](https://dri.es/connecting-drupal-with-activepieces).

### Upgrading the Activepieces Docker container

Activepieces regularly releases new versions. The Docker instance on your local machine does not update itself automatically, so you'll want to manually upgrade it from time to time.

First, list your running containers to find the container ID for Activepieces:

```bash
docker ps
```

Next, stop that container by replacing `<container-id>` with the actual ID you found:

```bash
docker stop <container-id>
```

Finally, pull the latest Activepieces image from Docker Hub:

```bash
docker pull activepieces/activepieces:latest
```

Start a new container using the same `docker run` command from above. Your flows and settings remain intact because they're stored in the mounted `~/.activepieces` directory.
