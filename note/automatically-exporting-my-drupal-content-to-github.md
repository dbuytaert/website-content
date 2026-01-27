---
url: 'https://dri.es/automatically-exporting-my-drupal-content-to-github'
title: 'Automatically exporting my Drupal content to GitHub'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-01-24T08:54:08-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: note
tags:
  - Drupal
  - 'Acquia Cloud'
  - Automation
  - 'My site'
published: true
featured: false
id: 6071
---

# Automatically exporting my Drupal content to GitHub

This note is mostly for my future self, in case I need to set this up again. I'm [sharing it publicly](https://dri.es/if-a-note-can-be-public-it-should-be) because parts of it might be useful to others, though it's not a complete tutorial since it relies on a custom Drupal module I haven't released.

For context: I [switched to Markdown](https://dri.es/switching-to-markdown-after-20-years-of-html) and then [open-sourced my blog content](https://dri.es/i-open-sourced-my-blog-content) by exporting it to GitHub. Every day, my Drupal site exports its content as Markdown files and commits any changes to [github.com/dbuytaert/website-content](https://github.com/dbuytaert/website-content). New posts appear automatically, and so do edits and deletions.

### Creating the GitHub repository

Create a new [GitHub](https://github.com/) repository. I called mine `website-content`.

### Giving your server access to GitHub

For your server to push changes to GitHub automatically, you need SSH key authentication.

SSH into your server and generate a new SSH key pair:

```bash
ssh-keygen -t ed25519 -f ~/.ssh/github -N ""
```

This creates two files: `~/.ssh/github` (your private key that stays on your server) and `~/.ssh/github.pub` (your public key that you share with GitHub). 

The `-N ""` creates the key without a passphrase. For automated scripts on secured servers, passwordless keys are standard practice. The security comes from restricting what the key can do (a deploy key with write access to one repository) rather than from a passphrase.

Next, tell SSH to use this key when connecting to GitHub:

```bash
cat >> ~/.ssh/config << 'EOF'
Host github.com
  IdentityFile ~/.ssh/github
  IdentitiesOnly yes
EOF
```

Add GitHub's server fingerprint to your known hosts file. This prevents SSH from asking "Are you sure you want to connect?" when the script runs:

```bash
ssh-keyscan github.com >> ~/.ssh/known_hosts
```

Display your public key so you can copy it:

```bash
cat ~/.ssh/github.pub
```

In GitHub, go to your repository's "Settings", find "Deploy keys" in the sidebar, and click "Add deploy key". Check the box for "Allow write access".

Test that everything works:

```bash
ssh -T git@github.com
```

You should see: `You've successfully authenticated, but GitHub does not provide shell access.`

### The export script

I created the following export script:

```bash
#!/bin/bash
set -e

TEMP=/tmp/dries-export

# Clone the existing repository
git clone git@github.com:dbuytaert/website-content.git $TEMP
cd $TEMP

# Clean all directories so moved/deleted content is tracked
rm -rf */

# Export all content older than 2 days
drush node:export --end-date="2 days ago" --destination=$TEMP

# Commit and push if there are changes
git config user.email "dries+bot@buytaert.net"
git config user.name "Dries Bot"
git add -A
git diff --staged --quiet || {
    git commit -m "Automatic updates for $(date +%Y-%m-%d)"
    git push
}

rm -rf $TEMP
```

The `drush node:export` command comes from a custom Drupal module I built for my site. I have _not_ published the module on Drupal.org because it's specific to my site and not reusable as is. I wrote about why that kind of code is still worth sharing as [adaptable modules](https://dri.es/adaptable-drupal-modules-code-meant-to-be-adapted-not-installed), and I hope to share it [once Drupal.org has a place for them](https://www.drupal.org/project/drupalorg/issues/3563839).

The two-day delay (`--end-date="2 days ago"`) gives me time to catch typos before posts are archived to GitHub. I usually find them right after hitting publish.

The `git add -A` stages everything including deletions, so if I remove a post from my site, it disappears from GitHub too (though Git's history preserves it).

### Scheduling the export

On a traditional server, you'd add this script to [Cron](https://en.wikipedia.org/wiki/Cron) to run daily. My site runs on [Acquia Cloud](https://dri.es/acquia-cloud-next-a-journey-in-platform-modernization), which is Kubernetes-based and automatically scales pods up and down based on traffic. This means there is no single server to put a crontab on. Instead, Acquia Cloud provides a scheduler that runs jobs reliably across the infrastructure. 

And yes, this note about automatically backing up my content will itself be automatically backed up.
