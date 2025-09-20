**Git & GitHub Workflow**

**What is Git and GitHub?**

**Git**

Git is a **distributed version control system (DVCS)** used to track changes in source code during software development. It allows multiple developers to work on a project simultaneously, manage changes, and maintain a history of modifications.

**How Git Works?**

**1.	Local Repository & Remote Repository:**

o	Git maintains a local repository on your machine and can sync with a remote repository (e.g., GitHub, GitLab, Bitbucket).

**2.	Snapshots Instead of Deltas:**

o	Unlike older VCS like SVN, which track differences between file versions, Git stores **snapshots** of the entire project at every commit.

**3.	Three States in Git:**

**o	Working Directory** → The actual files you are editing.

**o	Staging Area (Index)** → A place where you prepare files before committing.

**o	Repository** → The committed files that are saved in Git history.

**Basic Git Workflow**

1.	Modify files in the **working directory.**
  
2.	Stage the files using git add to move them to the **staging area.**
  
3.	Commit the files using git commit to save them in the **repository.**
  
4.	Push the changes to a **remote repository** like GitHub using git push.

---

**What is GitHub?**

GitHub is a cloud-based **Git repository hosting service** that allows developers to:

•	Store Git repositories online.

•	Collaborate with team members.

•	Use features like pull requests, issues, and CI/CD workflows.

**GitHub Workflow**

**1. GitHub Repository Setup**

•	A repository (**repo**) is a storage location for code.

•	Can be **public** (anyone can see) or **private** (only invited users can see).

**2. GitHub Branching Strategy**

•	**Main Branch** (main or master) → The stable, production-ready branch.

•	**Feature Branch** (feature/*) → A branch created for developing a new feature.

•	**Develop Branch** (develop) → An integration branch for merging feature branches before deploying.

•	**Hotfix Branch** (hotfix/*) → A branch for urgent bug fixes.

**Common Git Branching Workflow**

1.	Create a **feature branch** from main:

```bash
git checkout -b feature-new-feature
```

2.	Make changes and commit:

```bash
git add .
git commit -m "Added a new feature"
```

3.	Push the branch to GitHub:

  ```bash
git push -u origin feature-new-feature
```

4.	Create a **Pull Request (PR)** on GitHub to merge changes into main.
  
5.	Review and approve the PR.
  
6.	Merge PR and delete the feature branch.

---

**3. GitHub Workflow: Collaboration Process**

**Step 1: Fork and Clone a Repository**

•	**Fork**: Create a personal copy of someone else's repo.

•	**Clone**: Copy the repository to a local machine.

```bash
git clone https://github.com/username/repository.git
```

**Step 2: Creating a Feature Branch**

•	A new branch helps prevent conflicts when multiple people work on the same project.

```bash
git checkout -b new-feature
```

**Step 3: Making Changes and Committing**

•	After making changes:

```bash
git add .
git commit -m "Implemented new feature"
```

**Step 4: Pushing Changes to GitHub**

•	Push the local branch to GitHub.

```bash
git push origin new-feature
```

**Step 5: Creating a Pull Request (PR)**

•	Navigate to GitHub and open a PR.

•	The team reviews the code.

•	If approved, the PR is merged into main.

**Step 6: Merging and Deleting Branch**

•	After merging, delete the branch:

```bash
git branch -d new-feature
git push origin --delete new-feature
```

---

---

**Project Scenario: DevOps Automation Using GitHub**

**Team Members**

•	**Sharath** (Senior DevOps Engineer)

•	**Developer A** (Feature Developer)

•	**Developer B** (Bug Fixing & Testing)

**GitHub Repository**

•	**Project Name**: devops-automation

•	**Branches**:

o	**main** → Production-ready stable branch.

o	**develop** → Integration branch where all features are merged before being pushed to main.

o	**feature-branch** → Branches for new features.

o	**hotfix-branch** → Emergency bug fix branches.

---

**Step-by-Step GitHub Workflow**

**1. Clone the Repository**

Before making any changes, developers need to clone the repository to their local machine.

```bash
git clone https://github.com/org/devops-automation.git
cd devops-automation
git checkout -b develop
```

**2. Create a New Feature Branch**

Suppose **Developer A** is working on an **Ansible Playbook update**. He creates a new branch from develop:

```bash
git checkout -b feature-ansible-update develop
```

**3. Work on the Feature and Add Changes**

Developer A writes a new **Ansible Playbook** and modifies existing scripts.

```bash
vim ansible-playbook.yml
git add ansible-playbook.yml
git commit -m "Added Ansible playbook for automated deployments"
```

**4. Push Changes to GitHub**

After committing locally, Developer A pushes the feature branch to GitHub:

```bash
git push origin feature-ansible-update
```

---

**5. Create a Pull Request (PR)**

•	Developer A goes to GitHub and opens a **Pull Request (PR)** from feature-ansible-update to develop.

•	The team reviews the code and adds comments.

•	If changes are needed, Developer A updates the branch:

```bash
git add .
git commit --amend -m "Fixed Ansible playbook issues"
git push origin feature-ansible-update --force
```

**6. Merge the Pull Request**

Once the team approves the PR, Bharath merges it into develop:

```bash
git checkout develop
git merge feature-ansible-update
git push origin develop
```

---

**7. Test & Deploy from develop to main**

•	**Developer B** runs tests using GitHub Actions.

•	If tests pass, they merge develop into main for deployment:

```bash
git checkout main
git merge develop
git push origin main
```

•	The **CI/CD pipeline** automatically deploys the latest changes.

---

**8. Hotfix Scenario**

If a **critical bug** is found in production, Bharath creates a hotfix branch:

```bash
git checkout -b hotfix-db-connection main
```

•	Fixes the issue.

•	Pushes it to GitHub:

```bash
git add .
git commit -m "Fixed database connection timeout issue"
git push origin hotfix-db-connection
```

•	Creates a **Pull Request** and merges it into main & develop.
