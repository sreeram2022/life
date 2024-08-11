---
title: Server 
description: My ubuntu server setup
slug: server
date: 2024-08-04
image: 
categories:
    - Tech
tags:
    - linux
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---
# Ubuntu Server on an Old Lenovo Laptop

**Ubuntu Server** is a specialized version of the Ubuntu operating system, tailored for servers and data centers. Unlike its desktop counterpart, it doesn't have a GUI by default, making it lightweight and ideal for server tasks.

Recently, I installed Ubuntu Server on my old Lenovo laptop.

## Setup Process

1. **Download Ubuntu Server ISO**: Download the latest Ubuntu Server ISO file from the official Ubuntu website.
   
2. **Create a Bootable USB Drive**: I've used Etcher to create a bootable USB drive with the Ubuntu Server ISO.
   
3. **Boot from the USB Drive**: Insert the bootable USB into your laptop and boot from it.
   
4. **Install Ubuntu Server**: Follow the straightforward installation process:
   - Choose your language and keyboard layout.
   - Configure your network settings, select the installation drive, and set up the storage configuration.
   - Create a user account and set a password.
   - Select the software you want to install (I've chosen OpenSSH server for remote access).
   - Review your choices and start the installation process.

## Post-Installation Setup

After installation, update and upgrade the system:

```bash
sudo apt update
sudo apt upgrade
```
You can access your server using this command
```bash
sftp rama@192.168.0.104 
```
Replace the IP address with your server's IP.

* Access through File Manager: You can also access the server through a file manager for easier navigation. If you're on a Linux, this will be free and straightforward. On macOS and windows, you need third-party software for this.

* Terminal Access: Alternatively, you can access the server and perform necessary operations directly through the terminal.


## Basic SFTP commands

```bash
put <file>        # Upload files to the server
put -r <folder>   # Upload an entire folder (first create a folder with the same name on the server)
get <file>        # Download files from the server
bye               # Exit from the server
```
![sftp](b.png) 


## plex
Plex is a popular media server and client application that allows users to centralize their media content on a server and access it from various devices both locally and remotely.

Remote Access:
* Allows you to access your media library from anywhere with an internet connection.
* Securely share your media library with friends and family.

![plex](p.jpeg) 

I can access our plex media server through http://192.168.0.118:32400/web.
But I couldn’t properly configured plex. So I left it for future todo.
Anyway I can access my local server using vpn, I’ll probably setup later.


