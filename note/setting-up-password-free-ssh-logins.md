---
url: 'https://dri.es/setting-up-password-free-ssh-logins'
title: 'Setting up password-free SSH logins'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2024-06-07T07:02:30-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: note
tags:
  - Security
published: true
id: 5621
---

# Setting up password-free SSH logins

Setting up a new computer or device for secure, password-free logins not only streamlines automation processes but also improves security. Password-free authentication methods, such as public key authentication, reduce the risk of brute force attacks and phishing, as they eliminate the need to enter a password that could potentially be intercepted or guessed.

Because I keep forgetting how to set this up, I decided to document the steps for future reference.

### Step 1: Generate an SSH key on your control machine

If you don't already have an SSH key, create one with this command:

```shell
$ ssh-keygen -t rsa -b 2048
```

This will generate a 2048-bit RSA key. Follow the prompts to specify a file location and password.

### Step 2: Copy your public key to the target machine

Transfer your public key to the target machine, which is the computer you want to log into:

```shell
$ ssh-copy-id user@machine.local
```

This command appends your public key to the `~/.ssh/authorized_keys` file on the target machine.

Replace `user` with your username and `machine.local` with the target machine's hostname or IP address.

### Step 3: Configure `sshd` for passwordless logins

Disable password authentication and enable public key authentication for the ssh deamon on the target machine. First, log into the target machine, then edit the SSH configuration file, typically located at `/etc/ssh/sshd_config`. Ensure the following lines are set correctly:

```shell
PubkeyAuthentication yes
PasswordAuthentication no
```

After updating the configuration, restart the SSH daemon:

```shell
sudo systemctl restart sshd
```

**Note:** Ensure your public key has been correctly set up on the target machine before making these changes. Failure to do so may result in being unable to log in.

### Step 4: Load the key into your SSH agent

To automate authentication and avoid having to enter your password, we need to load the SSH key into the SSH agent. The SSH agent securely stores your keys and handles the authentication process, streamlining your workflow:

```shell
$ ssh-add ~/.ssh/id_rsa
```

That is it!
