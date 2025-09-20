# Deploy a Node.js "Hello World" App on AWS EC2: A Complete DevOps Guide

## Introduction

Deploying web applications on cloud platforms like AWS is a core skill for any DevOps or Cloud Engineer. In this tutorial, you'll learn how to deploy a basic Node.js "Hello World" application on an AWS EC2 instance. This hands-on project helps you understand the core DevOps practices: provisioning cloud infrastructure, managing access with IAM, connecting securely using SSH, configuring your app, and exposing it to the internet.

Whether you're preparing for DevOps interviews, looking to grow your GitHub portfolio, or just want to get started with real-world AWS projects—this guide is for you.

---

## Table of Contents

1. [Prerequisites](#prerequisites)  
2. [Create the Node.js App](#create-the-nodejs-app)  
3. [Launch an EC2 Instance](#launch-an-ec2-instance)  
4. [Connect to EC2 via SSH](#connect-to-ec2-via-ssh)  
5. [Install Node.js and Git](#install-nodejs-and-git)  
6. [Clone and Run the App on EC2](#clone-and-run-the-app-on-ec2)  
7. [Expose the App to the Internet](#expose-the-app-to-the-internet)  
8. [Best Practices](#best-practices)  
9. [Conclusion](#conclusion)

---

## Prerequisites

- AWS account with Free Tier access  
- Basic knowledge of Linux commands and Git  
- SSH client (Linux/macOS terminal or PuTTY on Windows)  
- A GitHub account to store your Node.js app  

---

## Create the Node.js App

1. On your local machine, create a directory:

```bash
mkdir hello-node-app && cd hello-node-app
```

2. Initialize a Node.js project:

```bash
npm init -y
```

3. Create an `index.js` file:

```javascript
// index.js
const http = require('http');

const hostname = '0.0.0.0';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, DevOps World from AWS EC2!\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

4. Add a start script in `package.json`:

```json
"scripts": {
  "start": "node index.js"
}
```

5. Push this code to a new GitHub repository (e.g., `hello-node-ec2`).

---

## Launch an EC2 Instance

1. Go to the AWS Console → EC2 → Launch Instance  
2. Choose:
   - AMI: Ubuntu 22.04 LTS  
   - Instance Type: `t2.micro` (Free Tier)  
   - Key Pair: Create a new one and download the `.pem` file  
   - Network: Allow **SSH (port 22)** and **Custom TCP (port 3000)** from `0.0.0.0/0`  
3. Launch the instance

---

## Connect to EC2 via SSH

Open your terminal and run:

```bash
chmod 400 your-key.pem
ssh -i "your-key.pem" ubuntu@<your-ec2-public-ip>
```

Once connected, you're inside your cloud-hosted virtual server.

---

## Install Node.js and Git

Update and install required packages:

```bash
sudo apt update
sudo apt install nodejs npm git -y
```

Verify installation:

```bash
node -v
npm -v
git --version
```

---

## Clone and Run the App on EC2

1. Clone your GitHub repository:

```bash
git clone https://github.com/your-username/hello-node-ec2.git
cd hello-node-ec2
```

2. Install dependencies and start the app:

```bash
npm install
npm start
```

If you see this message:

```
Server running at http://0.0.0.0:3000/
```

Your app is now running inside the EC2 instance.

---

## Expose the App to the Internet

1. Go to EC2 → Security Groups → Inbound Rules  
2. Add a new rule:
   - Type: Custom TCP  
   - Port: `3000`  
   - Source: `0.0.0.0/0` (for global access)

3. Now open a browser and visit:

```
http://<your-ec2-public-ip>:3000
```

You should see:  
`Hello, DevOps World from AWS EC2!`

---

## Best Practices

- Don’t hardcode sensitive credentials—use environment variables  
- Never expose ports in production without firewall or API Gateway  
- Use a domain name with HTTPS (Route 53 + ACM) for real apps  
- Set up a reverse proxy (e.g., Nginx) and use PM2 for production  
- Monitor EC2 usage to avoid unexpected costs  

---

## Conclusion

Congratulations. You've just deployed a real Node.js application on AWS EC2 from scratch. This hands-on exercise taught you how to:

- Write and host a Node.js app  
- Launch and SSH into EC2  
- Install dependencies  
- Expose services over the internet  

This project is perfect for your GitHub portfolio, resume, or even a DevOps blog post. Try replacing the app with a more complex one or automating the entire process with Ansible or Terraform.
