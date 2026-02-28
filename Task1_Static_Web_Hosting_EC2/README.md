# Task 1 – Static Web Hosting in EC2 (Ubuntu + Nginx)

## Objective
The objective of this task was to deploy a basic static website on an Ubuntu EC2 instance using the Nginx web server in AWS.

---

## Overview

In this task, I created a virtual server using Amazon EC2 and configured it to host a static website. I installed and configured Nginx as the web server and verified that the website was accessible through the public IP address of the EC2 instance.

---

## Steps Performed

1. Launched an EC2 instance  
   - Selected Ubuntu Server 22.04 LTS  
   - Chose instance type t3.micro (Free Tier eligible)  
   - Configured Security Group to allow:
     - SSH (Port 22)
     - HTTP (Port 80)

2. Connected to the instance  
   - Used the downloaded key pair (.pem file)
   - Connected securely using SSH from Git Bash

3. Updated the system packages  
   - Refreshed the package list before installation

4. Installed Nginx  
   - Installed Nginx web server using apt
   - Started the Nginx service
   - Enabled it to start automatically on reboot

5. Verified Nginx installation  
   - Checked service status using systemctl
   - Confirmed it was active and running

6. Modified the default web page  
   - Edited the default file located at:
     /var/www/html/index.html
   - Added custom HTML content

7. Tested the website  
   - Opened the EC2 Public IP in browser
   - Confirmed that the custom web page was successfully displayed

---

## Commands Used

sudo apt update  
sudo apt install nginx -y  
sudo systemctl start nginx  
sudo systemctl enable nginx  
sudo systemctl status nginx  
sudo nano /var/www/html/index.html  

---

## Screenshots Included

- EC2 instance running
- Nginx service status showing "active (running)"
- Default Nginx welcome page
- Custom website output in browser

---

## Outcome

This task helped me understand how to:
- Launch and configure an EC2 instance
- Connect to a Linux server using SSH
- Install and manage a web server (Nginx)
- Host a static website on AWS

The website was successfully deployed and accessed using the public IP address of the EC2 instance.
