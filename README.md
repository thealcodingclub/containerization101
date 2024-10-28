# Introduction to Docker & Containerization Workshop

Welcome to the Docker basics workshop! This guide will help you set up everything you need before we begin. Don't worry if you're new to all of this - we'll take it step by step.

## Prerequisites

### Required Software
1. **Docker Desktop**
   - For Windows: [Download Docker Desktop](https://www.docker.com/products/docker-desktop/)
   - For Mac: [Download Docker Desktop](https://www.docker.com/products/docker-desktop/)
   - For Linux: Follow the [Docker Engine installation guide](https://docs.docker.com/engine/install/)

2. **Git**
   - Windows: [Download Git](https://git-scm.com/download/windows)
   - Mac: Install via Terminal using `brew install git` (requires [Homebrew](https://brew.apple.com/))
   - Linux: `sudo apt-get install git` (Ubuntu/Debian) or `sudo yum install git` (CentOS/RHEL)



### Verifying Your Installation

After installing Docker, open your terminal/command prompt and run these commands to verify everything is working:

```bash
# Check Docker version
docker --version

# Verify Docker is running properly
docker run hello-world
```

If both commands run successfully, you're ready for the workshop!


## Common Installation Issues & Solutions

### Windows
1. **WSL 2 not enabled**
   - Open PowerShell as Administrator
   - Run: `wsl --install`
   - Restart your computer

2. **Virtualization not enabled**
   - Enter BIOS settings on startup
   - Enable virtualization (VT-x for Intel, AMD-V for AMD)

### Mac
1. **Docker Desktop failing to start**
   - Ensure you have the latest version
   - Try resetting Docker to factory defaults

### Linux
1. **Permission denied when running Docker commands**
   - Add your user to the docker group:
     ```bash
     sudo usermod -aG docker $USER
     ```
   - Log out and back in for changes to take effect

## Getting Help

If you encounter any issues during setup:
1. Check our [troubleshooting guide](link-to-troubleshooting.md)
2. Open an issue in this repository
3. Email us at alcoding@pes.edu

## Workshop Outline (Preview)

Here's what we'll cover in the workshop:
1. Introduction to containerization
2. Overview of Docker 
3. Basic Docker commands
4. Creating your first container
5. Building custom images
6. Working with Docker Compose
 

Looking forward to seeing you at the workshop! 🐳

---
*Note: Please complete the setup at least one day before the workshop to ensure we can help you with any issues.*
