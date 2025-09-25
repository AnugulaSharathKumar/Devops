# Interview Questions:

**1. What is devops?**

DevOps is a set of practices, culture, and tools that bring development (Dev) and operations (Ops) teams together to deliver software faster, more reliably, and with higher quality.
DevOps encourages collaboration, automation, and continuous feedback across the entire software lifecycle — from coding → testing → deployment → monitoring.

**2. CI/Cd Follow**

![My Diagram](<img width="1366" height="768" alt="Screenshot (2)" src="https://github.com/user-attachments/assets/8efc0132-772e-4b59-b388-ac128a99ee4b" />)

<img width="1366" height="768" alt="Screenshot (2)" src="https://github.com/user-attachments/assets/4d3507f0-9b96-442c-b34b-38d17ede557b" />

**3. ⚙️ Common DevOps Tools:**

**Version Control:** Git, GitHub, GitLab, Bitbucket

**CI/CD:** Jenkins, GitHub Actions, GitLab CI, Azure DevOps

**Configuration Management:** Ansible, Puppet, Chef

**Containers & Orchestration:** Docker, Kubernetes

**Monitoring & Logging:** Prometheus, Grafana, ELK Stack, Splunk

**Security (DevSecOps):** Trivy, SonarQube, Snyk
_____

**4. Git Questions**

1. Git Conflicts:

A conflict happens when two or more people change the same part of a file, or when Git cannot automatically merge changes. Developers must manually resolve the conflict before committing.

2. Git Rebase

git rebase is used to move or reapply commits from one branch on top of another branch.
It creates a cleaner, linear commit history.

Example: git rebase main applies your feature branch commits on top of main.

3. Git Merge

git merge combines changes from one branch into another.
It preserves the commit history as it is.

Example: git merge feature-branch merges all changes into the current branch.

4. Git Push

git push uploads your local commits to a remote repository (like GitHub, GitLab, Bitbucket).

Example: git push origin main pushes your local main branch to the remote origin.

5. Git Stash (not “statsh”)

git stash temporarily saves uncommitted changes (modified/unstaged files) without committing them. This lets you work on something else and reapply them later.

Example:

git stash → saves your work

git stash pop → restores it back

**5. Git branching strategy**
A Git branching strategy is a workflow that defines how teams use branches in Git to collaborate, manage features, fix bugs, and release code. The goal is to keep the codebase stable, organized, and easy to manage.

🔑 Common Git Branching Strategies
1. Git Flow

Branches used:

main (production-ready code)

develop (integration of features)

feature/* (new features)

release/* (pre-release testing)

hotfix/* (urgent production fixes)

Best for: Large projects with planned releases.

✅ Clear structure, supports CI/CD

❌ Can be heavy for small teams

2. GitHub Flow

Branches used:

main (always deployable)

feature/* (short-lived branches)

Developers branch from main, make changes, then open a Pull Request (PR). After review, code merges back into main.

Best for: Continuous deployment, smaller teams.

✅ Simple and lightweight

❌ Limited structure for release cycles

3. GitLab Flow

Combines GitHub Flow + environment branches.

Branches used:

main

feature/*

production, staging (environment-specific)

Best for: Teams using CI/CD pipelines with multiple environments.

4. Trunk-Based Development

Branches used:

main (or trunk) only

Short-lived feature branches merged daily

Developers integrate small changes continuously into main.

Best for: Fast-moving teams, DevOps, CI/CD heavy environments.

✅ Very fast releases, less merge conflicts

❌ Requires discipline & strong CI/CD

**7. Linux Commands**

**🔹 1. AWK- (Aho Weinberger Kernighan)**

A powerful text-processing tool used to extract, filter, and format data from files or command output.

Syntax:

```sh
awk '{print $1}' file.txt
 ```
**🔹 2. grep**
Used to search for patterns (strings, regex) inside files or command output.

Syntax:

```sh
grep "error" app.log
 ```

**🔹 3. find**

Used to search for files/directories in a filesystem based on name, size, time, permissions, etc.

Syntax:

```sh
find /var/log -name "*.log"
find / -size +100M
find . -name "*.tmp" -delete
```
