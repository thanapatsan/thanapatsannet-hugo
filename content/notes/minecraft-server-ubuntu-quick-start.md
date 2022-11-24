---
title: minecraft server quick start
summary: >
  minecraft server quick start guide

date: 2021-08-09T10:18:36.504Z 

tags: 
  - Minecraft
  - Server
  - Ubuntu
---

quick note on how to create a minecraft server on ubuntu  
using commonly available VPS services such as [DigitalOcean](https://m.do.co/c/ce13f779b449) or whatever you might have  

hosting a very basic vanila server for 2-10 players  
recommended to have at least 4GB RAM (1 for system, 3 for Minecraft)  
always use latest LTS version of your OS  

## usual update and stuff

```bash
apt update
apt upgrade
```

## getting java 16 for minecraft 1.17+

```bash
apt install openjdk-16-jre-headless
```

## opening firewall to minecraft server 

```bash
ufw allow 25565

ufw enable
```

## add seperate user

honestly no idea why, saw one guide does it for security reason.

```bash
useradd -m -r -d /opt/minecraft minecraft
```

## switch to minecraft server user

```bash
su - minecraft
```

## download minecraft server file

```bash
wget -O /opt/minecraft/minecraft_server.jar [put server file link here]
```

## go to server directory

```bash
cd /opt/minecraft
```

## call server to generate starter file

```bash
java -Xmx1G -Xms1G -jar minecraft_server.jar nogui initSettings
```

## give permission to minecraft server user

```bash
chown -R minecraft /opt/minecraft
```

## actually running the game server (with 3gb ram)

```bash
java -Xmx3G -Xms3G -jar minecraft_server.jar nogui
```

---

### read more stuff

Initial Server Setup with Ubuntu 20.04  
https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04

Getting started with Tmux  
https://linuxize.com/post/getting-started-with-tmux/

Tmux Cheat Sheet & Quick Reference  
https://tmuxcheatsheet.com/