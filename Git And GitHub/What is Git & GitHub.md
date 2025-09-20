**Git and GitHub:**
**version control systems (VCS)** are essential tools for tracking changes, enabling collaboration, and maintaining code quality. As part of the **DevOps**, this article provides an in-depth look at the concepts of **Git** and **GitHub**, the difference between centralized and distributed version control systems, and how DevOps engineers can effectively use Git in their workflows.


**Q: What is the difference between centralized and distributed version control systems?**

A: Centralized systems rely on a single server for code sharing. Distributed systems like Git allow each user to maintain a full copy of the code, enabling offline access and parallel collaboration.
________________________________________

**Git vs GitHub**

| Git                               | GitHub                                                |
|----------------------------------|--------------------------------------------------------|
| Open-source version control tool | Web-based hosting platform for Git repositories       |
| Installed on local machines or self-hosted servers | Hosted by GitHub Inc. (cloud-based)      |
| Used for tracking changes in source code | Adds collaboration features like issues, pull requests, CI/CD integration, and project boards |

________________________________________

**Hands-On: Git Basics**

**Step 1: Install Git**

```sh
# Ubuntu / Debian
sudo apt update && sudo apt install git

# RHEL / CentOS / Oracle Linux
sudo yum install git
```

Verify installation:

```sh
git --version
```
________________________________________
**Step 2: Initialize a Git Repository**

```sh
mkdir example.com
cd example.com
git init
```

A .git/ directory is created, which stores all versioning information.
________________________________________
**Step 3: Track and Commit Changes**

Create a file:

```sh
vim calculator.sh
```

Add simple code:

```sh
x=a+b
```

Check repository status:

```sh
git status
```

Add file to staging:

```sh
git add calculator.sh
```

Commit your changes:

```sh
git commit -m "Initial commit: addition feature"
```
________________________________________
**Step 4: Make and Track Modifications**

Edit the file:

```sh
vim calculator.sh
# Change to: x=a+b+c
```

Check what changed:

```sh
git diff
```

Stage and commit:

```sh
git add calculator.sh
git commit -m "Added support for three-number addition"
```
________________________________________
**Step 5: View Commit History**

```sh
git log
```

Output shows commit hashes, authors, and messages.
________________________________________
**Step 6: Roll Back to a Previous Version**

```sh
git reset --hard <commit_hash>
```

Use this to revert to a previous stable state.
________________________________________


**Step 1: Create a GitHub Account**

Go to (https://github.com/) and sign up.
________________________________________
**Step 2: Create a New Repository**

•	Click on **New Repository**

•	Name: devops-calculator

•	Initialize with README (optional)

•	Set visibility: Public or Private

•	Click **Create Repository**
________________________________________
**Step 3: Push Local Repo to GitHub**

```sh
git remote add origin https://github.com/<username>/devops-calculator.git
git branch -M main
git push -u origin main
```
Your code is now on GitHub and ready to be shared with your team.
