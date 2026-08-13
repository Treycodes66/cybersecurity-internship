# Task 2: Basic Firewall Configuration with UFW

## Overview

In this task, I configured UFW (Uncomplicated Firewall) on a Linux system to control incoming and outgoing network traffic.

The main purpose was to create a simple firewall configuration that blocks unwanted inbound connections while still allowing services that are required, such as SSH.

## Environment

- **Operating System:** Linux
- **Firewall:** UFW (Uncomplicated Firewall)
- **Protocol:** TCP
- **SSH Port:** 22
- **HTTP Port:** 80

## Configuration

I started by setting the default incoming policy to `deny` and the outgoing policy to `allow`. This means that incoming connections are blocked unless a specific rule allows them, while outgoing connections are allowed.

I then added the following firewall rules:

- **SSH (TCP/22):** Allowed so that I can connect to the Linux system remotely.
- **HTTP (TCP/80):** Denied to prevent incoming HTTP traffic.

After configuring the rules, I enabled UFW and verified the configuration using the firewall status commands.

## Commands Used

```bash
sudo apt update
sudo apt install ufw -y

sudo ufw default deny incoming
sudo ufw default allow outgoing

sudo ufw allow ssh
sudo ufw deny 80/tcp

sudo ufw enable
sudo ufw status verbose
