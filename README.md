 ✅ GitHub Folder Structure


docker-devops-task/
│
├── README.md                        # Main report file with all steps
├── html/                            # For best practice demo (custom page)
│   └── index.html
├── docker-compose.yml              # (optional advanced part)
└── Dockerfile                       # (optional, if custom image is created)

 ## Docker DevOps Task – Web Server

 🔍 Objectives
- Learn Docker containerization basics
- Deploy and manage a web server inside Docker
- Understand container lifecycle and commands
- Monitor container health and troubleshoot issues
- Explore container deployment best practices

---

## 📁 1. Learn Docker Containerization Basics

**Installed Docker on Ubuntu EC2:**

sudo apt update
sudo apt install docker.io -y


**Verified Installation:**

docker --version


## 🌐 2. Deploy and Manage a Web Server Inside Docker

**Run NGINX container:**


docker run -d -p 80:80 --name my-nginx nginx


## 🔁 3. Understand Container Lifecycle

Basic Docker commands used:


docker ps
docker stop my-nginx
docker start my-nginx
docker restart my-nginx
docker logs my-nginx
docker rm my-nginx





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




<img width="960" alt="server01" src="https://github.com/user-attachments/assets/b1555189-23b9-4527-8289-bc6cff66b565" />

<img width="960" alt="server02" src="https://github.com/user-attachments/assets/9b24cf0c-94e2-4e0a-a393-0397b650808c" />

<img width="960" alt="server03" src="https://github.com/user-attachments/assets/ed1cc574-262d-4675-a8c2-c1fef5cd5e82" />

<img width="753" alt="server04" src="https://github.com/user-attachments/assets/bafbce6f-79e2-4d69-a486-401f3da9c38a" />

<img width="960" alt="server06" src="https://github.com/user-attachments/assets/d544558e-5749-4407-aff9-3d94829ebce1" />

<img width="797" alt="server07" src="https://github.com/user-attachments/assets/a575a444-8d82-4065-9a45-babf1df20eb1" />

<img width="806" alt="server08" src="https://github.com/user-attachments/assets/86b2fe09-7665-476f-9d05-cb98f510254c" />




