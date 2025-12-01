---
title: 'Setting up an Activepieces development environment'
date: '2025-11-07T04:35:18-05:00'
author: Dries
tags:
  - Drupal
  - Activepieces
published: true
type: note
url: /setting-up-an-activepieces-development-environment
id: 5926
---

If you just want to use [Activepieces](https://www.activepieces.com/) with [Drupal](https://www.drupal.org/) on your local development machine, the easiest option is to follow my guide on [running Activepieces locally with Docker](https://dri.es/running-activepieces-locally-with-docker). That approach allows you to use Activepieces, but you can't make code changes to it. 

If you want to contribute to the [Drupal Piece](https://www.activepieces.com/pieces/drupal) integration or create a new Piece, the Docker setup won't work. To develop or modify Pieces, you'll need to set up a full Activepieces development environment, which this note explains.

First, fork the Activepieces repository on GitHub using the UI. Then clone your fork locally:

```shell
git clone https://github.com/YOUR-USERNAME/activepieces.git
```

Move into the project directory and install all dependencies:

```shell
cd activepieces
npm install
```

By default, the development setup only builds a limited set of components. To include the Drupal Piece, open `./packages/server/api/.env` and add "drupal" to the `AP_DEV_PIECES` variable.

Next, start your local development instance:

```shell
npm start
```

Open your web browser and go to [http://localhost:4200](http://localhost:4200).

Sign in with the default development account:

* Email: `dev@ap.com`
* Password: `12345678`

This account is preconfigured so you can start building and testing custom Pieces right away. 

The Drupal Piece code lives in `./packages/pieces/community/drupal`. 

When you make changes to the code, they're automatically compiled and hot-reloaded, so you can see your changes immediately without restarting the development server.

To complete your setup, see my guide on [connecting Drupal with Activepieces](https://dri.es/connecting-drupal-with-activepieces).

### Troubleshooting common issues

I've run into a few issues while working with the Activepieces development environment. Here is what usually fixes them.

Start by deleting all caches:

```shell
rm -rf node_modules cache dev
```

This removes `node_modules` (all installed dependencies), `cache` (build and runtime caches), and `dev` (temporary development files).

Activepieces uses [Nx](https://nx.dev/), an open source build system for monorepos. If Nx's cache is out of sync, reset it to start with a clean slate for builds and tests:

```shell
npx nx reset
```
