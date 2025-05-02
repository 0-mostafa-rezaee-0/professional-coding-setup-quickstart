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

***Table of Contents***

<details>
  <summary><a href="#1-about-this-repository"><i><b>1. About This Repository</b></i></a></summary>
  <div>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#11-who-is-this-tutorial-for">1.1. Who Is This Tutorial For?</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#12-what-will-you-learn">1.2. What Will You Learn?</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#13-prerequisites">1.3. Prerequisites</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#14-project-structure">1.4. Project Structure</a><br>
  </div>
</details>
&nbsp;

<details>
  <summary><a href="#2-windows"><i><b>2. Windows</b></i></a></summary>
  <div>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#21-install-wsl">2.1. Install WSL</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#22-create-user--password">2.2. Create user & password</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#23-install-git">2.3. Install Git</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#24-install-zsh--oh-my-zsh">2.4. Install Zsh & Oh-My-Zsh</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#25-configure-ssh--passkeys">2.5. Configure SSH & passkeys</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#26-install-docker">2.6. Install Docker</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#27-install-github-cli-gh">2.7. Install GitHub CLI (gh)</a><br>
  </div>
</details>
&nbsp;

<details>
  <summary><a href="#3-macos"><i><b>3. macOS</b></i></a></summary>
  <div>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#31-install-git">3.1. Install Git</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#32-install-zsh--oh-my-zsh">3.2. Install Zsh & Oh-My-Zsh</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#33-configure-ssh--passkeys">3.3. Configure SSH & passkeys</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#34-install-docker">3.4. Install Docker</a><br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#35-install-github-cli-gh">3.5. Install GitHub CLI (gh)</a><br>
  </div>
</details>
&nbsp;

<div>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#4-contact-information"><i><b>4. Contact Information</b></i></a>
</div>
&nbsp;

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

WSL (Windows Subsystem for Linux) creates a genuine Linux environment directly within Windows, without the overhead of a virtual machine. This is critical for professional development as it provides access to Linux tools, utilities, and command-line applications that are standard in the industry. Most deployment environments run Linux, so developing in a similar environment reduces "works on my machine" issues.

1. Open PowerShell as Administrator
2. Run the command:
   ```powershell
   wsl --install
   ```
3. Restart your computer
4. WSL will finish the installation process automatically after restart

## 2.2. Create user & password

Setting up a dedicated user account in your Linux environment establishes proper file permissions and security practices. This separation reflects real-world server configurations and builds good habits for professional development, where proper user management is essential for security and access control.

When WSL first launches, you'll be prompted to create a username and password:

```
Enter new UNIX username: your_username
New password:
Retype new password:
```

Even a simple password like "/" is acceptable as this is only for your local development environment.

## 2.3. Install Git

Git is the industry-standard version control system used by virtually all professional development teams. It allows tracking changes, collaborating with others, and maintaining a complete history of your codebase. Git's distributed nature means you can work offline while still having the full project history, and its branching model enables parallel development workflows.

```bash
sudo apt update
sudo apt install git -y
git --version
```

### 2.3.1. Git Commands (frequently used)

**Step 3:** Daily workflow commands (used in sequence)
```bash
1. git pull                                      # Pull latest changes from remote repository
2. git status                                    # Check status of working directory
3. git add .                                     # Stage all changes for commit
4. git status                                    # Verify staged changes
5. git commit -m "A relevant title for the commit"  # Commit staged changes with a descriptive message
6. git push                                      # Push commits to remote repository
```

**Step 2:** Clone an existing repository (once per repository)
```bash
# Clone a repository
git clone git@gitlab.com:mostafa.mohammadrezaee/git-commands.git
cd repo
```

**Step 1:** Create a new repository (once per repository)
```bash
# Create a new repository on GitHub and clone it.
```

### 2.3.2. Professional Git Configuration

For recommended Git configuration, follow these steps in order:

1. Set VS Code as the default editor for Git
   ```bash
   git config --global core.editor "code --wait"
   ```

2. Edit Git configuration file
   ```bash
   git config --global --edit
   ```

   After the file opens, add or edit these settings (replace "your name" and "your gmail" with your actual name and email, and "username" with your Linux username):
   ```bash
   [user]
     name = your name
     email = your gmail
   
   [init]
     defaultBranch = main
   
   [core]
     excludesfile = /home/username/.gitignore_global
     editor = code --wait
   
   [diff]
     editor = code --wait
   
   [difftool "vscode"]
     cmd = code --wait --diff $LOCAL $REMOTE
   ```

### 2.3.3. Best Practices for .gitignore

Setting up a proper .gitignore configuration helps keep your repository clean by excluding temporary files, build artifacts, and environment-specific files from version control.

**One-time setup (steps 1-4):**

1. Create a global .gitignore file:
   ```bash
   touch ~/.gitignore_global
   ```

2. Configure Git to use this global file:
   ```bash
   git config --global core.excludesfile ~/.gitignore_global
   ```

3. Create a comprehensive .gitignore using [gitignore.io](https://www.gitignore.io/) with the following settings:
   - python
   - jupyternotebooks
   - visualstudiocode
   - linux
   - windows
   - macos
   - venv

4. Add the following custom entries at the top of the file:
   ```
   # Two Sections: 
   ## Section 1: Created by authors
   ## Section 2: Created by gitignore.io

   # Section 1--------------------------------------------------
   # Created by authors 

   tree.txt

   # To prevent Zone.Identifier files
   *Zone.Identifier

   # Conda environments
   *.conda
   *.env
   *.envs
   .env/
   .envs/

   # Section 2--------------------------------------------------
   # Created by gitignore.io
   ```

**For each new repository (steps 5-7):**

5. Create a project-specific .gitignore and copy the global settings:
   ```bash
   cat ~/.gitignore_global >> .gitignore
   ```

6. To add new global rules, manually edit the global .gitignore file and add entries to Section 1.

7. For project-specific exclusions, add them to the top of the project's .gitignore file:
   ```
   # Section 0--------------------------------------------------
   # Project-specific rules
   ```

## 2.4. Install Zsh & Oh-My-Zsh

Zsh (Z Shell) is a powerful shell with improved features over the basic Bash shell, including better autocompletion, spelling correction, and plugin support. Oh-My-Zsh extends Zsh with a framework of plugins, themes, and helpers that dramatically improve your command-line productivity. Professional developers rely on efficient terminal workflows, and this combination provides substantial quality-of-life improvements.

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

SSH (Secure Shell) is the standard protocol for securely accessing remote servers and services. Setting up SSH keys eliminates the need for passwords when connecting to remote systems or services like GitHub. Passkeys represent the next evolution in authentication security, offering phishing-resistant, hardware-backed credentials. Together, they create a more secure and convenient workflow for professional developers who frequently interact with remote systems.

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

Docker creates isolated containers that package applications with all their dependencies, ensuring consistent behavior across different environments. This solves the "it works on my machine" problem by providing a consistent runtime regardless of host system differences. For professional development, Docker enables efficient testing, simplified deployment, and collaboration by ensuring everyone uses identical environments.

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

GitHub CLI (gh) brings the GitHub workflow directly to your terminal, eliminating the need to switch between browser and code editor. This command-line tool lets you create issues, manage pull requests, and perform other GitHub actions without leaving your terminal. For professionals, this streamlines workflow and keeps you focused on coding rather than context-switching between tools.

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

### 2.7.1. Practical GitHub CLI Commands

**Repository Management:**
```bash
# List repositories
gh repo list

# Create a new repository
gh repo create my-project --public

# Clone a repository
gh repo clone owner/repository

# Fork a repository
gh repo fork owner/repository

# View repository details
gh repo view owner/repository
```

**Issue Management:**
```bash
# List open issues
gh issue list

# Create a new issue
gh issue create --title "Bug: Login page not working" --body "Description of the issue"

# View an issue
gh issue view ISSUE_NUMBER

# Close an issue
gh issue close ISSUE_NUMBER
```

**Pull Request Workflow:**
```bash
# Create a pull request
gh pr create --title "Feature: Add login functionality" --body "Description of the changes"

# List open pull requests
gh pr list

# View a pull request
gh pr view PR_NUMBER

# Check out a pull request locally
gh pr checkout PR_NUMBER

# Merge a pull request
gh pr merge PR_NUMBER
```

**Release Management:**
```bash
# Create a new release
gh release create v1.0.0 --title "Version 1.0.0" --notes "Release notes here"

# List releases
gh release list

# Download release assets
gh release download TAG_NAME
```

---

# 3. macOS

VS Code is the go-to editor for most professionals; the best practice is to launch it from the terminal for seamless integration with your development environment.

## 3.1. Install Git

Git is the industry-standard version control system used by virtually all professional development teams. It allows tracking changes, collaborating with others, and maintaining a complete history of your codebase. Git's distributed nature means you can work offline while still having the full project history, and its branching model enables parallel development workflows.

1. Install Homebrew if not already installed:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Install Git:
   ```bash
   brew install git
   git --version
   ```

### 3.1.1. Git Commands (frequently used)

**Step 3:** Daily workflow commands (used in sequence)
```bash
1. git pull                                      # Pull latest changes from remote repository
2. git status                                    # Check status of working directory
3. git add .                                     # Stage all changes for commit
4. git status                                    # Verify staged changes
5. git commit -m "A relevant title for the commit"  # Commit staged changes with a descriptive message
6. git push                                      # Push commits to remote repository
```

**Step 2:** Clone an existing repository (once per repository)
```bash
# Clone a repository
git clone git@gitlab.com:mostafa.mohammadrezaee/git-commands.git
cd repo
```

**Step 1:** Create a new repository (once per repository)
```bash
# Create a new repository on GitHub and clone it.
```

### 3.1.2. Professional Git Configuration

For recommended Git configuration, follow these steps in order:

1. Set VS Code as the default editor for Git
   ```bash
   git config --global core.editor "code --wait"
   ```

2. Edit Git configuration file
   ```bash
   git config --global --edit
   ```

   After the file opens, add or edit these settings (replace "your name" and "your gmail" with your actual name and email, and "username" with your macOS username):
   ```bash
   [user]
     name = your name
     email = your gmail
   
   [init]
     defaultBranch = main
   
   [core]
     excludesfile = /Users/username/.gitignore_global
     editor = code --wait
   
   [diff]
     editor = code --wait
   
   [difftool "vscode"]
     cmd = code --wait --diff $LOCAL $REMOTE
   ```

### 3.1.3. Best Practices for .gitignore

Setting up a proper .gitignore configuration helps keep your repository clean by excluding temporary files, build artifacts, and environment-specific files from version control.

**One-time setup (steps 1-4):**

1. Create a global .gitignore file:
   ```bash
   touch ~/.gitignore_global
   ```

2. Configure Git to use this global file:
   ```bash
   git config --global core.excludesfile ~/.gitignore_global
   ```

3. Create a comprehensive .gitignore using [gitignore.io](https://www.gitignore.io/) with the following settings:
   - python
   - jupyternotebooks
   - visualstudiocode
   - linux
   - windows
   - macos
   - venv

4. Add the following custom entries at the top of the file:
   ```
   # Two Sections: 
   ## Section 1: Created by authors
   ## Section 2: Created by gitignore.io

   # Section 1--------------------------------------------------
   # Created by authors 

   tree.txt

   # To prevent Zone.Identifier files
   *Zone.Identifier

   # Conda environments
   *.conda
   *.env
   *.envs
   .env/
   .envs/

   # Section 2--------------------------------------------------
   # Created by gitignore.io
   ```

**For each new repository (steps 5-7):**

5. Create a project-specific .gitignore and copy the global settings:
   ```bash
   cat ~/.gitignore_global >> .gitignore
   ```

6. To add new global rules, manually edit the global .gitignore file and add entries to Section 1.

7. For project-specific exclusions, add them to the top of the project's .gitignore file:
   ```
   # Section 0--------------------------------------------------
   # Project-specific rules
   ```

## 3.2. Install Zsh & Oh-My-Zsh

Zsh (Z Shell) is a powerful shell with improved features over the basic Bash shell, including better autocompletion, spelling correction, and plugin support. Oh-My-Zsh extends Zsh with a framework of plugins, themes, and helpers that dramatically improve your command-line productivity. Professional developers rely on efficient terminal workflows, and this combination provides substantial quality-of-life improvements.

1. Zsh is the default shell on modern macOS. Verify with:
   ```bash
   echo $SHELL
   ```

2. Install Oh-My-Zsh:
   ```bash
   sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

## 3.3. Configure SSH & passkeys

SSH (Secure Shell) is the standard protocol for securely accessing remote servers and services. Setting up SSH keys eliminates the need for passwords when connecting to remote systems or services like GitHub. Passkeys represent the next evolution in authentication security, offering phishing-resistant, hardware-backed credentials. Together, they create a more secure and convenient workflow for professional developers who frequently interact with remote systems.

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

Docker creates isolated containers that package applications with all their dependencies, ensuring consistent behavior across different environments. This solves the "it works on my machine" problem by providing a consistent runtime regardless of host system differences. For professional development, Docker enables efficient testing, simplified deployment, and collaboration by ensuring everyone uses identical environments.

1. Download Docker Desktop for Mac from [Docker's website](https://www.docker.com/products/docker-desktop/)
2. Install the downloaded .dmg file
3. Verify installation:
   ```bash
   docker --version
   docker run hello-world
   ```

## 3.5. Install GitHub CLI (gh)

GitHub CLI (gh) brings the GitHub workflow directly to your terminal, eliminating the need to switch between browser and code editor. This command-line tool lets you create issues, manage pull requests, and perform other GitHub actions without leaving your terminal. For professionals, this streamlines workflow and keeps you focused on coding rather than context-switching between tools.

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

