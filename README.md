# 🐳 Docker DevOps Task – Web Server Deployment

## 🔍 Objectives
- Learn Docker containerization basics
- Deploy and manage a web server inside Docker
- Understand container lifecycle and commands
- Monitor container health and troubleshoot issues
- Explore container deployment best practices

---

## 📁 1. Learn Docker Containerization Basics

**Installed Docker on Ubuntu EC2:**
```bash
sudo apt update
sudo apt install docker.io -y
docker --version

2 . Deploy and Manage a Web Server Inside Docker
Run NGINX container:

bash
Copy
Edit
docker run -d -p 80:80 --name my-nginx nginx
<img width="960" alt="server06" src="https://github.com/user-attachments/assets/2e64e03a-edde-448e-90f9-29d4ca450a87" />

