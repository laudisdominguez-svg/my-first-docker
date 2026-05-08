# my-first-docker 🐳

> Documentation of my first steps with Docker, including installation guide and learning tutorial.
A step-by-step educational guide for your **first Docker container on Windows** using WSL

This is my first Docker project: documenting the entire installation and configuration process, along with the satisfaction of seeing a container running in your local browser.


## 🎯 What Is This?

- ✅ A practical guide for installing Docker on Windows
- ✅ A beginner-friendly tutorial
- ✅ My first running container (Nginx)
- ✅ Solutions for common issues


** This is not a coding project — it’s learning documentation.**

## 📋 Requirements

- Windows 10 or 11
- PowerShell running as Administrator
- Internet connection
- Around 5–10 minutes of your time



## 📁 Repository Structure
```
my-first-docker/
└── README.md    ← Everything you need
└── screenshots
```

** That’s the entire project. Just documentation. Simple and straightforward. **

## 🚀 Quick Installation

## 1. Verify and Install WSL

```powershell
# View available distributions
wsl --list --online
# Install Ubuntu
wsl --install -d Ubuntu
# View installed distributions
wsl --list --verbose
```

### 2. Open Ubuntu
```powershell
wsl -d Ubuntu
```
You should see:
```
user@PC:~$
```

### 3. Install Docker
```bash
# Update packages
sudo apt-get update
# Install Docker
sudo apt-get install docker.io -y
# Verify installation
docker --version
```

### 4. Enable and Start Docker
```bash
# Enable Docker to start automatically
sudo systemctl enable docker
# Start the service
sudo systemctl start docker
```

### 5. Fix Permissions (If Necessary)

If you see `PERMISSION DENIED`:
```bash
# Add your user to the docker group
sudo usermod -aG docker your_user
# Option 1: Close and reopen Ubuntu
exit
# From PowerShell
wsl -d Ubuntu
# Option 2: Activate immediately
newgrp docker
# Verify it works
docker ps
```

### ✅ Your First Container

```bash
# Run Nginx
docker run -d -p 8080:80 nginx
# Verify it is running
docker ps
```
** Open your browser: http://localhost:8080

You should see the Nginx welcome page ✨

### 📚 Useful Commands
```bash
# View all containers (including stopped ones)
docker ps -a
# Stop a container
docker stop CONTAINER_ID
# Remove a container
docker rm CONTAINER_ID
# View logs
docker logs CONTAINER_ID
# Remove an image
docker rmi IMAGE_ID
```

### 🔧 Troubleshooting

### "docker: command not found"
→ Docker is not installed or you are not inside Ubuntu through WSL

### "Permission denied while trying to connect to Docker"
→ Your user is not in the docker group (follow Step 5)

### "Port 8080 already in use"
→ Use another port:
docker run -d -p 8081:80 nginx

### "Cannot connect to Docker daemon"
→ Start the service:
sudo systemctl start docker

## 📖 What Did You Learn?
After following this guide, you now understand:

- ✅ WSL allows Linux to run on Windows
- ✅ Docker packages applications into isolated containers
- ✅ Permissions matter in Linux
- ✅ Port mapping connects your machine to the container
- ✅ Docker Hub provides thousands of ready-to-use images
- ✅ How to verify everything is working correctly


## 🎓 Key Lessons

1. Documentation is your ally — every step should be verified
2. Errors are part of learning — “Permission denied” is normal
3. Docker simplifies deployment — one command = a working server
4. Learning should be celebrated — seeing Nginx in your browser feels amazing 🎉


## 🔗 References

- [Docker Official Documentation] (https://docs.docker.com)
- [WSL Documentation] (https://learn.microsoft.com/en-us/windows/wsl/)
- [Docker Hub — Official Images] (https://hub.docker.com)
- [Nginx Docker Image] (https://hub.docker.com/_/nginx)


## 📝 Notes

- This project is educational and beginner-focused
- Perfect for Windows developers starting with Docker
- Tested on Windows 11 + Ubuntu 22.04
- If you encounter issues, check the troubleshooting section


## 🌟 Next Steps
Once you master this:

1. Build your own custom Dockerfile
2. Explore Docker Compose for multi-container setups
3. Publish your own images on Docker Hub
4. Share your knowledge with other beginners


## 📄 License
Educational content free to use and share. Help others learn Docker too.
---

**Did it work for you?** If this guide helped, leave a ⭐ on GitHub!
**Have questions?** Open an issue or leave a comment on DEV.to.
**Successfully ran your first container?** Congratulations — you just entered the world of Docker 🐳🎉
