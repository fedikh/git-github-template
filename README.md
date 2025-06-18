# Git Version Control System Course

![Git Logo](https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png)

## 📋 Course Overview

Welcome to the complete Git Version Control System course! This repository contains everything you need to master Git from basics to advanced concepts.

### What You'll Learn
- **Git Fundamentals**: Tracking changes in files
- **Collaborative Development**: Working with teams efficiently  
- **Speed & Data Integrity**: Fast, reliable version control
- **Distributed Workflows**: Working with local and remote repositories
- **GitHub Integration**: Managing repositories on GitHub

---

## Part 1: Introduction to Git

### 🎯 What is Distributed Version Control?

In distributed version control systems like Git:
- Every developer has a **complete copy** of the repository (code + full history)
- **No central server** required for most operations (unlike centralized systems like SVN)
- Collaboration happens by **sharing changes** via push, pull, and fetch operations

### 🎯 Why Choose Git?

✅ **Fast Performance** - Lightning-fast operations  
✅ **Easy Branching & Merging** - Create and merge branches effortlessly  
✅ **Offline Capability** - Work without internet connection  
✅ **Reliability** - Used by major tech companies worldwide  
✅ **Open Source** - Free and community-driven  

---

## Part 2: Basic Git Workflow

### ⚙️ Step 1: Configure Git

Set your identity for all repositories:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### ⚙️ Step 2: Initialize a Git Repository

```bash
git init
```
*Creates a new `.git` directory where Git stores repository data*

### ⚙️ Step 3: Understanding File States

Git tracks files in four states:
- **Untracked** - File not under Git control
- **Unmodified** - File tracked and unchanged
- **Modified** - File changed but not staged
- **Staged** - File marked to be committed

Check current status:
```bash
git status
```

### ⚙️ Step 4: Default Branch

- Git creates a default branch called `master` (or `main` in recent versions)

### ⚙️ Step 5: Staging Files

Add specific files:
```bash
git add 
```

Add all files:
```bash
git add .
```

### ⚙️ Step 6: Commit Changes

```bash
git commit -m "Your descriptive commit message"
```

### ⚙️ Step 7: View Changes

```bash
git diff
```
*Shows differences between working directory and staging area*

### ⚙️ Step 8: Reset Operations

Unstage a file (keep changes):
```bash
git reset 
```

⚠️ **Destructive Reset** (removes all changes):
```bash
git reset --hard
```

### 🌱 Basic Workflow Summary

```bash
# Initialize repository
git init

# Configure Git
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Stage files
git add 

# Commit changes
git commit -m "Commit message"

# View differences
git diff

# Reset if needed
git reset 
```

---

## Part 3: Remote Repositories (GitHub)

A **remote repository** is your project hosted online (GitHub, GitLab, Bitbucket) for:
- **Collaboration** with team members
- **Sharing** your work publicly
- **Backup** of your code

### Adding Remote Repository

```bash
git remote add origin https://github.com/username/repository-name.git
```

### View Remote URLs

```bash
git remote -v
```

📖 **Reference**: [Git - Working with Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)

---

## Part 4: Working with Remote Repositories

### 🌀 Clone Repository

```bash
git clone https://github.com/username/repository-name.git
```
*Downloads repository and sets origin as remote*

### 🌀 Check Remote Connections

```bash
git remote -v
```

### 🌀 List All Branches

```bash
git branch -a
```
*Shows local and remote branches*

### 🌀 Fetch Remote Changes

```bash
git fetch origin
git diff master origin/master
```
*Fetch updates and compare local vs remote*

### 🌀 Merge Changes

```bash
git merge origin/master
```

### 🌀 Pull Changes (Fetch + Merge)

```bash
git pull
```

### 🌀 Push Changes

```bash
git push origin master
```

### 🌀 Forking Repositories

On GitHub:
1. Navigate to repository
2. Click **Fork** button
3. Creates your own copy

📖 **Reference**: [GitHub Docs - Fork a Repository](https://docs.github.com/en/get-started/quickstart/fork-a-repo)

### 🌀 Template Repositories

GitHub allows creating template repositories that others can use as starting points.

📖 **Reference**: [GitHub Docs - Creating a Template Repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository)

---

## Part 5: Branching and Merging

### 🌿 Understanding Git Commits

- A commit is a **snapshot** + metadata (author, message, parent commits)
- Each commit points to a **tree object** representing project state

### 🌿 Create and Switch Branches

Create branch:
```bash
git branch feature-branch
git checkout feature-branch
```

Create and switch in one command:
```bash
git checkout -b feature-branch
```

### 🌿 View Commit History

```bash
git log --oneline --decorate
```

### 🌿 Fast-Forward Merging

When branch is directly ahead of base (no divergence):
```bash
git merge feature-branch
```

### 🌿 Three-Way Merge (ORT Strategy)

Standard Git merge strategy using common ancestor:
```bash
git merge feature-branch
```

### 🌿 Resolving Merge Conflicts

#### Manual Resolution:
1. Edit conflicting files
2. Mark conflicts as resolved:
```bash
git add 
git commit
```

#### Using Merge Tool (KDiff3):
```bash
git mergetool
```
*Requires KDiff3 installation and configuration*

📖 **Reference**: [Git Book - Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)

---

## Part 6: Pull Request Workflow

### 🔑 Complete Pull Request Process

#### 1. Create Remote Repository
- On GitHub: Click **New Repository** → **Create**

#### 2. Clone Repository
```bash
git clone https://github.com/username/repository-name.git
```

#### 3. Create Application
Create your project (language-specific):
```bash
# Node.js
npm init

# .NET
dotnet new console

# Python
touch main.py
```

#### 4. Configure .gitignore
Create `.gitignore` file:
```bash
touch .gitignore
```

Example contents:
```gitignore
# Node.js
node_modules/
npm-debug.log*

# Python
__pycache__/
*.pyc
*.pyo

# .NET
bin/
obj/
*.user

# General
.DS_Store
*.log
```

#### 5. Initial Commit to Master
```bash
git add .
git commit -m "Initial commit: Project setup"
git push origin master
```

#### 6. Create Feature Branch
```bash
git checkout -b refactor-branch
# Make your changes here
git add .
git commit -m "Refactor: Improve code structure"
git push origin refactor-branch
```

#### 7. Create Pull Request
1. Go to GitHub repository
2. Click **Compare & Pull Request**
3. Add description and submit

#### 8. Merge Pull Request
1. Review the PR
2. Click **Merge Pull Request**
3. Confirm merge

📖 **Reference**: [GitHub Docs - About Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

---

## 🚀 Quick Reference Commands

### Essential Commands
```bash
# Repository Management
git init
git clone 
git status
git log

# Staging and Committing  
git add 
git commit -m "message"
git diff

# Branching
git branch 
git checkout 
git checkout -b 
git merge 

# Remote Operations
git remote add origin 
git push origin 
git pull origin 
git fetch origin
```

### Configuration
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --list
```

---

## 📚 Additional Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Learning Lab](https://lab.github.com/)
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)
- [Interactive Git Tutorial](https://learngitbranching.js.org/)

---

## 🏆 Course Completion Checklist

- [ ] Configure Git with your identity
- [ ] Initialize your first repository
- [ ] Make commits with meaningful messages
- [ ] Create and work with branches
- [ ] Resolve merge conflicts
- [ ] Work with remote repositories
- [ ] Create and merge pull requests
- [ ] Use .gitignore effectively

---

## 🤝 Contributing

Found an error or want to improve this course? Feel free to:
1. Fork this repository
2. Create a feature branch
3. Make your improvements
4. Submit a pull request

---

## 📝 License

This course material is open source and available under the [MIT License](LICENSE).

---

**Happy Learning! 🎉**

*Master Git step by step and become a version control expert!*
