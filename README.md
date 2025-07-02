 ✅ GitHub Folder Structure


docker-devops-task/
│
├── README.md                        # Main report file with all steps
├── screenshots/                     # All evidence images
│   ├── docker-version.png
│   ├── nginx-browser.png
│   ├── docker-ps.png
│   ├── docker-health.png
│   ├── docker-stats.png
│   └── volume-page.png
├── html/                            # For best practice demo (custom page)
│   └── index.html
├── docker-compose.yml              # (optional advanced part)
└── Dockerfile                       # (optional, if custom image is created)
```

 🐳 Docker DevOps Task – Web Server Deployment

 🔍 Objectives
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
````

**Verified Installation:**

```bash
docker --version


## 🌐 2. Deploy and Manage a Web Server Inside Docker

**Run NGINX container:**

```bash
docker run -d -p 80:80 --name my-nginx nginx


## 🔁 3. Understand Container Lifecycle

Basic Docker commands used:

```bash
docker ps
docker stop my-nginx
docker start my-nginx
docker restart my-nginx
docker logs my-nginx
docker rm my-nginx
```




## 🧠 4. Monitor Container Health and Troubleshoot

**Health Monitoring:**

```bash
docker inspect my-nginx | grep Status
docker stats
```

**Add healthcheck while launching:**

```bash
docker run -d -p 8080:80 --name nginx-health \
--health-cmd='curl -f http://localhost/' \
--health-interval=30s --health-retries=3 nginx
```


## 🛠️ 5. Explore Container-Based App Deployment Best Practices

### ➤ Volume Mounting for Static Site

```bash
mkdir -p /home/ubuntu/html
echo "<h1>Hello from Docker Volume</h1>" > /home/ubuntu/html/index.html
```

**Run with volume:**

```bash
docker run -d -p 8081:80 -v /home/ubuntu/html:/usr/share/nginx/html \
--name custom-nginx nginx
```


### ➤ Optional: Use Docker Compose

```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8082:80"
```

Run:

```bash
docker-compose up -d
```

---

## ✅ Conclusion

* ✔ Docker installed
* ✔ NGINX container deployed
* ✔ Lifecycle commands executed
* ✔ Health monitored
* ✔ Best practices followed (volume + docker-compose)




