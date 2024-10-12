# Virtual Web Hosting Using NGINX
# Project Name: **Nginx HTML Website Deployment on VM**

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Prerequisites](#prerequisites)
- [Installation and Setup](#installation-and-setup)
- [Deployment](#deployment)
- [Accessing the Website](#accessing-the-website)
- [Troubleshooting](#troubleshooting)

## Project Overview
This project demonstrates the deployment of a static HTML website on an **Nginx** web server hosted on an **Ubuntu Virtual Machine**. The primary objective is to serve static web content via the Nginx server.

## Technologies Used
- **Nginx** - High-performance web server
- **Ubuntu** - Virtual machine operating system
- **HTML/CSS/JavaScript** - Website structure and design
- **Virtual Machine (VM)** - Hosting environment

## Prerequisites
Before starting the deployment, ensure you have the following:
- An **Ubuntu VM** instance running.
- Access to the VM via **SSH**.
- Basic knowledge of Linux terminal commands.
- Installed **Nginx** on the VM.

### Required Tools
- **SSH Client** (Git Bash)
- **Text Editor** (VS Code)
- **Web Browser** (for testing)

## Installation and Setup

### Step 1: Install Nginx on the Virtual Machine
Run the following commands to install and start Nginx:
```bash
sudo apt update
sudo apt install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
```
### Step 2: Clone the Repository from GitHub
Clone the GitHub repository containing your HTML files:

```bash
git clone https://github.com/yourusername/your-repo.git
```
Note: Replace https://github.com/yourusername/your-repo.git with the actual URL of your GitHub repository.

### Step 2: Configure Firewall

Allow traffic on HTTP and HTTPS:

```bash
sudo ufw allow 'Nginx Full'
sudo ufw enable
```

### Step 3: Add Your HTML Website

Upload your HTML files to the Nginx web root directory. 

To do this, use the following command:

```bash
sudo cp -r /path/to/your/html/files/* /var/www/html/
```

### Step 4: Verify Nginx Configuration

After adding your HTML files to the Nginx web root directory, it’s important to verify the Nginx configuration to ensure everything is set up correctly.

1. **Check Nginx Configuration**

   Run the following command to test the Nginx configuration for any syntax errors:

   ```bash
   sudo nginx -t
   ```
2. **If no errors are found, restart Nginx:**

   Run the following command to test the Nginx configuration for any syntax errors:

   ```bash
   sudo systemctl restart nginx
   ```
### Step 5: Test the Website

Once all configurations are done, you can access the website using your Virtual Machine’s public IP address.

Open a web browser and navigate to:

   ```bash
   http://20.84.65.234
   ```

 Note : Need to use the ip address of respective V.M which was created by you.

---

## Step 5: Troubleshooting

- **Nginx not serving the website**: Check the status of Nginx:
  ```bash
  sudo systemctl status nginx
  ```

- **Permission issues:**: Ensure the correct ownership and permissions for your website files:
  ```bash
  sudo chown -R www-data:www-data /var/www/html
  sudo chmod -R 755 /var/www/html
  ```

- **Firewall issues:**:  Verify that the firewall is allowing HTTP and HTTPS traffic:
  ```bash
  sudo ufw status
  ```
---


