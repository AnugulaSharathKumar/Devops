# Interview Questions:

**1. What is devops?**

DevOps is a set of practices, culture, and tools that bring development (Dev) and operations (Ops) teams together to deliver software faster, more reliably, and with higher quality.
DevOps encourages collaboration, automation, and continuous feedback across the entire software lifecycle — from coding → testing → deployment → monitoring.

**2. CI/Cd Follow**

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
**4. scp (Secure Copy)**

Used to copy files securely between local and remote systems (uses SSH).
Syntax:
```sh
scp user@server:/home/user/file.txt /local/path/
scp file.txt user@server:/home/user/
```
___
🔹 Basic Jenkins Interview Questions

1. What is Jenkins?
👉 Jenkins is an open-source automation server used for continuous integration and continuous delivery (CI/CD). It automates building, testing, and deploying software.

2. What are the key features of Jenkins?

Open source, extensible with 1800+ plugins

Distributed builds (master–agent architecture)

Pipeline as Code (Jenkinsfile with Groovy)

Integrates with Git, Maven, Docker, Kubernetes, etc.

Supports CI/CD workflows

3. Difference between Jenkins Freestyle and Pipeline jobs?

Freestyle Job → GUI-based, simple, limited flexibility.

Pipeline Job → Code-driven (Jenkinsfile, Groovy), supports complex workflows, reusable, version-controlled.

🔹 Intermediate Jenkins Questions

4. Explain Jenkins Master-Slave (Controller-Agent) architecture.

Master/Controller → Orchestrates jobs, schedules builds, manages UI.

Slave/Agent → Executes build jobs on different platforms/environments.

Useful for scaling and distributing workloads.

5. What is a Jenkinsfile?
👉 A text file that defines the Jenkins Pipeline using Groovy DSL, stored in source control.
Example:

pipeline {
    agent any
    stages {
        stage('Build') { steps { sh 'mvn clean install' } }
        stage('Test') { steps { sh 'mvn test' } }
        stage('Deploy') { steps { sh './deploy.sh' } }
    }
}


6. How do you secure Jenkins?

Enable authentication (LDAP, SSO, AD, GitHub OAuth)

Use Role-Based Access Control (RBAC)

Secure Jenkins master with HTTPS

Restrict CLI/remote builds

Regular plugin updates

Run Jenkins with limited OS permissions

7. What are Jenkins shared libraries?
👉 A way to create reusable pipeline code.

Stored in a Git repo

Can be loaded in Jenkinsfile:

@Library('my-shared-lib') _

🔹 Advanced Jenkins Questions

8. How do you handle secrets in Jenkins?

Use Jenkins Credentials Plugin

Inject secrets via environment variables or binding plugins

Integrate with Vault (HashiCorp), AWS Secrets Manager, Azure Key Vault, or Kubernetes Secrets

9. How do you achieve high availability (HA) in Jenkins?

Use Jenkins Operations Center (CloudBees) or set up HA with:

Active-passive setup with load balancer

Kubernetes-based Jenkins with persistence (e.g., Helm + StatefulSets)

Backup using plugins (ThinBackup, Job DSL export, GitOps approach)

10. How to integrate Jenkins with Docker and Kubernetes?

Docker: Build Docker images using docker build, push to registry.

Kubernetes:

Use Kubernetes Plugin to provision agents dynamically.

Deploy apps using kubectl or Helm inside Jenkins pipelines.

Run Jenkins itself inside Kubernetes.

11. How do you optimize Jenkins performance?

Use ephemeral agents (Docker/K8s)

Limit build history, rotate logs

Use distributed builds (scale horizontally)

Optimize pipeline scripts (parallel stages, caching)

Monitor with Prometheus + Grafana

12. Difference between Declarative and Scripted Pipeline?

Declarative:

More readable, structured syntax (pipeline {})

Easier for beginners, opinionated

Scripted:

Full Groovy flexibility (node {})

More powerful, but complex

🔹 Scenario-Based Questions

13. A build is failing intermittently. How do you troubleshoot?

Check Jenkins logs (/var/log/jenkins/jenkins.log)

Check workspace for leftover files → cleanup

Retry with pipeline retry() directive

Validate external dependencies (network, DB, APIs, test environments)

Use timestamps() and debug logging for better traceability

14. How do you handle parallel builds in Jenkins?

stage('Parallel Build') {
    parallel {
        stage('Unit Tests') { steps { sh 'mvn test' } }
        stage('Lint') { steps { sh 'npm run lint' } }
    }
}


15. How do you migrate Jenkins jobs from one server to another?

Backup and restore $JENKINS_HOME

Use Job DSL Plugin or Jenkins Configuration as Code (JCasC)

Store Jenkinsfiles in Git for portability

For plugins, maintain plugins.txt and re-install on new server

🔹 Jenkins with DevOps Tools

16. Jenkins + Git

Webhooks for CI/CD

Git plugins for checkout and branch-based pipelines

17. Jenkins + SonarQube

Integrate SonarQube plugin for code quality checks

Example:

withSonarQubeEnv('sonar-server') {
    sh 'mvn sonar:sonar'
}


18. Jenkins + Trivy (security scans)

Run trivy image <image> inside pipeline

Fail build if vulnerabilities are found

19. Jenkins + Terraform

Automate infrastructure provisioning

Validate and apply using:

sh 'terraform init'
sh 'terraform plan'
sh 'terraform apply -auto-approve'


20. Jenkins + Ansible

Use Ansible plugin or run playbooks via ansible-playbook command in pipeline
