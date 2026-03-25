---
title: A MollySocket Guide for the De-Googled Among Us
date: 2026-01-14 12:00:00 -500
categories: [homelab, services]
tags: [grapheneos, mollysocket]
---

## Introduction

For ten years as an iPhone user, I never once thought about how notifications actually work. They just... worked. Someone sends you a Signal message, Apple's servers tap your phone on the shoulder, and boom—notification. Seamless, efficient, battery-friendly. The perfect invisible infrastructure.
![Normal Notification Flow](/assets/mollysocket/normal_notifications.jpg){: width="50%" .center}

Then I switched to GrapheneOS, because privacy matters. And suddenly, I had to think about notifications. A lot.

Here's the thing about ditching the big tech ecosystem: you're on your own. Without Google's push notification system, your Signal app can't just wait politely for Apple or Google to relay messages. Instead, it has to constantly pester Signal's servers directly: "Got anything for me? No? How about now? Now? NOW?"

![Notifications without Google](https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExcTY5dW9ybWNjNTZqaGg2NzFhMXY1c3B6YTNscnNxOWJnd3BkdTd1YyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/WpC9IBZfmkuKTtVC58/giphy.gif)

Your de-Googled Signal app is essentially cosplaying as Donkey from Shrek, and your battery life suffers accordingly.

## Enter MollySocket

Molly is a hardened fork of Signal packed with privacy-focused features—database encryption with auto-lock, RAM shredding, the works. But one of its best tricks is MollySocket: a personal server that does all that annoying "are we there yet?" pestering _for_ you.

Here's how it works: MollySocket links to your Signal account like any other device, then constantly polls Signal for new messages. When something arrives, it notifies a Unified Push server, which notifies a Unified Push app on your phone who tells Molly "hey buddy, connect to Signal—you've got mail." Only then does your phone wake up and pull the actual message.

![Notification flow with mollysocket](/assets/mollysocket/mollysocket_flow.jpg){: width="50%" .center}

Sounds complicated, right? It's actually pretty straightforward to set up, and it'll save you significant battery life.

There are two deployment methods for MollySocket. Method one creates a web server but requires a reverse proxy. Method two skips the web server entirely—no reverse proxy needed. I went with option two because, well, I didn't have a reverse proxy lying around. The official documentation is solid, but I found it a bit light on details for this particular setup, so I'm filling in the gaps.

If you want to deploy MollySocket without the web server, this guide is for you.

Now grab yourself a cup of coffee, and let's get after it.

## Step 1: Install Molly and a Unified Push App

First, install Molly on your phone and set it up like you would regular Signal.

Next, you'll need a push notification app. I use the Accrescent app store, which offers Sunup—nice and simple, zero configuration required for Unified Push. Alternatively, you could use Ntfy, though that requires either configuring it to communicate with Ntfy's servers or spinning up your own Ntfy server.

Now for the fun part: building your MollySocket.

## Step 2: Set Up Your Server

Spin up a server somewhere. I used an Ubuntu VM on my Proxmox host at home, then installed Docker.

Never installed Docker? It's easier than you think. Just follow [Docker's official documentation](https://docs.docker.com/engine/install/ubuntu/).

## Step 3: Install MollySocket via Docker Compose

**Create a directory for your Molly files**

Out of habit, I like keeping my Docker directories in `/opt`, but you can use anywhere—even your home directory.
```bash
cd /opt
sudo mkdir Molly
cd Molly
```

**Pull the Docker image**
```bash
sudo docker pull ghcr.io/mollyim/mollysocket:latest
```

**Create your docker-compose.yml file**

Open your favorite text editor and paste this configuration:
```bash
sudo nano docker-compose.yml
```
```yaml
services:
  mollysocket:
    image: ghcr.io/mollyim/mollysocket:1
    container_name: mollysocket
    restart: always
    volumes:
      - ./data:/data
    working_dir: /data
    command: server
    environment:
      - MOLLY_DB="/data/mollysocket.db"
      # Do not add spaces in the array
      - MOLLY_ALLOWED_ENDPOINTS=["*"]
      - MOLLY_ALLOWED_UUIDS=["*"]
      # We'll add the VAPID key in the next step
      #- MOLLY_VAPID_PRIVKEY=""
      - MOLLY_HOST=0.0.0.0
      - MOLLY_PORT=8020
      - RUST_LOG=info
      # Set to airgap mode
      - MOLLY_WEBSERVER=false
    #ports:
    #  - "8020:8020"
```

**Generate and add your VAPID key**
```bash
sudo docker compose run --rm mollysocket mollysocket vapid gen
```

Copy the output and paste it into your `docker-compose.yml` file under `MOLLY_VAPID_PRIVKEY`. Your final config should look like this:
```yaml
services:
  mollysocket:
    image: ghcr.io/mollyim/mollysocket:1
    container_name: mollysocket
    restart: always
    volumes:
      - ./data:/data
    working_dir: /data
    command: server
    environment:
      - MOLLY_DB="/data/mollysocket.db"
      # Do not add spaces in the array
      - MOLLY_ALLOWED_ENDPOINTS=["*"]
      - MOLLY_ALLOWED_UUIDS=["*"]
      - MOLLY_VAPID_PRIVKEY="asdfasdfasdfjfasdfasdfasdf12345" #I made this VAPID up, use your own!
      - MOLLY_HOST=0.0.0.0
      - MOLLY_PORT=8020
      - RUST_LOG=info
      # Set to airgap mode
      - MOLLY_WEBSERVER=false
    #ports:
    #  - "8020:8020"
```

## Step 4: Link Your Phone

Run the container in the foreground to get the QR code:
```bash
sudo docker compose up
```

This command omits the `-d` flag, which makes the container run in the foreground—a necessity to display the QR code.

Open Molly on your phone and scan the QR code to link the device. Once you've scanned it, press Ctrl+C to stop the container.

## Step 5: Configure Unified Push

Now we need to tell MollySocket how to reach your phone.

In Molly's settings, find the Unified Push section and copy the connection parameters. Get them onto your computer (email yourself, use a pastebin, whatever works).

With the service stopped, run:
```bash
sudo docker compose run --rm mollysocket <paste your parameters here>
```

If everything's configured correctly, you should receive a test notification on your phone (assuming you've got Sunup or your chosen push distributor installed).

## Step 6: Fire It Up

Start the service one last time:
```bash
sudo docker compose up -d
```

**Congrats! You're done.**

Isn't this cool? There's something genuinely empowering about taking control of the whole notification pipeline and understanding what's happening behind the scenes. Plus, your battery will thank you.

Now go forth and enjoy your privacy-respecting, battery-efficient messaging setup. You've earned it.