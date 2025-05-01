## 🧰 How to Use This Template    
Click the green **"Use this template"** button at the top of the page, then choose **"Create a new repository"**.   
This will create your own copy of this project, which you can modify freely — no need to fork!   

---

<p align="center">
  <img src="images/banner.png" alt="banner" width="75%">
</p>

<h1 align="center">Professional Coding Setup Quickstart</h1>

Even seasoned pros will learn something new. Both Windows &amp; macOS: Git, Zsh, Oh-My-Zsh, SSH, passkeys, Docker, GitHub CLI (gh), and more. 

---

## Table of Contents
- [1. About This Repository](#1-about-this-repository)
  - [1.1. Who Is This Tutorial For?](#11-who-is-this-tutorial-for)
  - [1.2. What Will You Learn?](#12-what-will-you-learn)
  - [1.3. Prerequisites](#13-prerequisites)
  - [1.4. Project Structure](#14-project-structure)
- [2. Windows](#2-windows)
  - [2.1. Install WSL](#21-install-wsl)
  - [2.2. Create user & password](#22-create-user--password)
  - [2.3. Install Git](#23-install-git)
  - [2.4. Install Zsh & Oh-My-Zsh](#24-install-zsh--oh-my-zsh)
  - [2.5. Configure SSH & passkeys](#25-configure-ssh--passkeys)
  - [2.6. Install Docker](#26-install-docker)
  - [2.7. Install GitHub CLI (gh)](#27-install-github-cli-gh)
- [3. macOS](#3-macos)
  - [3.1. Install Git](#31-install-git)
  - [3.2. Install Zsh & Oh-My-Zsh](#32-install-zsh--oh-my-zsh)
  - [3.3. Configure SSH & passkeys](#33-configure-ssh--passkeys)
  - [3.4. Install Docker](#34-install-docker)
  - [3.5. Install GitHub CLI (gh)](#35-install-github-cli-gh)
- [4. Contact Information](#4-contact-information)

---

# 1. About This Repository

This repository provides a comprehensive guide to setting up a professional development environment on both Windows and macOS. It bridges the gap between casual coding and professional development by walking through industry-standard tools and practices that enhance productivity, collaboration, and code quality.

## 1.1. Who Is This Tutorial For?

This guide is designed for:
- Software developers transitioning from casual to professional development
- Computer Science students preparing for industry work
- Self-taught programmers looking to adopt professional workflows
- Experienced developers setting up a new system or standardizing their environment
- Teams establishing consistent development environments across members

No specific programming language knowledge is required, but basic familiarity with terminal/command-line operations is helpful.

## 1.2. What Will You Learn?

Following this guide, you will:
- Set up a Linux-based development environment on Windows via WSL
- Configure industry-standard shell environments with Zsh and Oh-My-Zsh
- Establish secure SSH authentication with modern passkeys
- Implement containerization with Docker for consistent development environments
- Use GitHub CLI to streamline Git workflow and collaboration
- Launch VS Code directly from your terminal for seamless integration

## 1.3. Prerequisites

Your prerequisites depend on your current experience level:

1. **For experienced developers**: You can quickly scan through the guide to identify any tools or configurations you haven't yet adopted.
2. **For developers new to professional setups**: Follow the guide sequentially, with extra attention to the SSH, Docker, and WSL sections.
3. **For beginners**: Take time to understand each tool before implementing it. The guide provides context for why each tool matters in professional environments.

Required:
- Administrative access to your computer
- Internet connection
- ~5GB of free disk space (for Docker and WSL installations)

## 1.4. Project Structure

```
Folder PATH listing
+---images                  <-- Contains visual assets
│       banner.png          <-- Main repository banner
│
│       .gitignore          <-- Git exclusion patterns
│       LICENSE             <-- Project license information
│       README.md           <-- This documentation file
```

---

# 2. Windows

VS Code is the go-to editor for most professionals; the best practice is to launch it from the terminal and keep all code inside a Linux-based folder structure. We'll set that up now.

## 2.1. Install WSL

1. Open PowerShell as Administrator
2. Run the command:
   ```powershell
   wsl --install
   ```
3. Restart your computer
4. WSL will finish the installation process automatically after restart

## 2.2. Create user & password

When WSL first launches, you'll be prompted to create a username and password:

```
Enter new UNIX username: your_username
New password:
Retype new password:
```

Even a simple password like "/" is acceptable as this is only for your local development environment.

## 2.3. Install Git

```bash
sudo apt update
sudo apt install git -y
git --version
```

## 2.4. Install Zsh & Oh-My-Zsh

1. Install Zsh:
   ```bash
   sudo apt install zsh -y
   ```

2. Install Oh-My-Zsh:
   ```bash
   sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

3. Make Zsh your default shell:
   ```bash
   chsh -s $(which zsh)
   ```

## 2.5. Configure SSH & passkeys

1. Generate SSH key:
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```

2. Start the SSH agent:
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

3. For FIDO2/WebAuthn passkey:
   ```bash
   ssh-keygen -t ecdsa-sk -C "your_email@example.com"
   ```

Follow GitHub's guide for adding SSH keys to your account: [GitHub Docs: Adding a new SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

## 2.6. Install Docker

1. Install Docker Engine in WSL:
   ```bash
   sudo apt update
   sudo apt install apt-transport-https ca-certificates curl software-properties-common
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
   sudo apt update
   sudo apt install docker-ce docker-ce-cli containerd.io
   ```

2. Add your user to the docker group:
   ```bash
   sudo usermod -aG docker $USER
   ```

3. Enable Docker Desktop WSL integration through Docker Desktop settings

## 2.7. Install GitHub CLI (gh)

1. Install GitHub CLI:
   ```bash
   curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
   echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
   sudo apt update
   sudo apt install gh
   ```

2. Authenticate:
   ```bash
   gh auth login
   ```

3. Verify by cloning a repository:
   ```bash
   gh repo clone owner/repository
   ```

---

# 3. macOS

VS Code is the go-to editor for most professionals; the best practice is to launch it from the terminal for seamless integration with your development environment.

## 3.1. Install Git

1. Install Homebrew if not already installed:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Install Git:
   ```bash
   brew install git
   git --version
   ```

## 3.2. Install Zsh & Oh-My-Zsh

1. Zsh is the default shell on modern macOS. Verify with:
   ```bash
   echo $SHELL
   ```

2. Install Oh-My-Zsh:
   ```bash
   sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

## 3.3. Configure SSH & passkeys

1. Generate SSH key:
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```

2. Start the SSH agent:
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

3. For FIDO2/WebAuthn passkey:
   ```bash
   ssh-keygen -t ecdsa-sk -C "your_email@example.com"
   ```

Follow GitHub's guide for adding SSH keys to your account: [GitHub Docs: Adding a new SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

## 3.4. Install Docker

1. Download Docker Desktop for Mac from [Docker's website](https://www.docker.com/products/docker-desktop/)
2. Install the downloaded .dmg file
3. Verify installation:
   ```bash
   docker --version
   docker run hello-world
   ```

## 3.5. Install GitHub CLI (gh)

1. Install GitHub CLI using Homebrew:
   ```bash
   brew install gh
   ```

2. Authenticate:
   ```bash
   gh auth login
   ```

3. Verify by cloning a repository:
   ```bash
   gh repo clone owner/repository
   ```

---

# 4. Contact Information

For questions not addressed in the resources above, please connect with [Mostafa Rezaee](https://www.linkedin.com/in/mostafa-rezaee/) on LinkedIn for personalized assistance.

