**Essential Git Commands that DevOps Engineers commonly use in their Day-to-Day activities:**

### Basic Commands

1. **Initialize a New Repository**
   
   ```sh
   git init
   ```
   Initializes a new Git repository in the current directory.

2. **Clone a Repository**
   
   ```sh
   git clone <repository_url>
   ```
   Clones a repository into a new directory.

3. **Add Changes to Staging Area**
   
   ```sh
   git add <file_or_directory>
   ```
   Adds a file or changes in a file to the staging area.

4. **Commit Changes**
   
   ```sh
   git commit -m "commit message"
   ```
   Records changes to the repository with a descriptive message.

5. **Check Repository Status**
   
   ```sh
   git status
   ```
   Displays the status of the working directory and staging area.

### Branch Management

6. **List Branches**
   
   ```sh
   git branch
   ```
   Lists all local branches in the current repository.

7. **Create a New Branch**
   
   ```sh
   git branch <branch_name>
   ```
   Creates a new branch.

8. **Switch to a Branch**
   
   ```sh
   git checkout <branch_name>
   ```
   Switches to the specified branch.

9. **Create and Switch to a New Branch**
    
   ```sh
   git checkout -b <branch_name>
   ```
   Creates a new branch and switches to it.

10. **Delete a Branch**
    
    ```sh
    git branch -d <branch_name>
    ```
    Deletes the specified branch.

### Remote Repository Management

11. **Add Remote Repository**
    
    ```sh
    git remote add <name> <url>
    ```
    Adds a new remote repository.

12. **List Remote Repositories**
    
    ```sh
    git remote -v
    ```
    Lists the remote repositories along with their URLs.

13. **Fetch Changes from Remote**
    
    ```sh
    git fetch <remote>
    ```
    Downloads objects and refs from another repository.

14. **Push Changes to Remote**
    
    ```sh
    git push <remote> <branch>
    ```
    Uploads local repository content to a remote repository.

15. **Pull Changes from Remote**
    
    ```sh
    git pull <remote> <branch>
    ```
    Fetches changes from the remote repository and merges them into the local branch.

### Merging and Rebasing

16. **Merge Branches**
    
    ```sh
    git merge <branch>
    ```
    Merges the specified branch's history into the current branch.

17. **Rebase Branch**
    
    ```sh
    git rebase <branch>
    ```
    Reapplies commits on top of another base tip, often used to integrate changes from one branch onto another cleanly.

18. **Abort Merge**
    
    ```sh
    git merge --abort
    ```
    Aborts the current conflict resolution process and tries to reconstruct the pre-merge state.

### Stashing and Cleaning

19. **Stash Changes**
    
    ```sh
    git stash
    ```
    Temporarily shelves (or stashes) changes that haven't been committed.

20. **Apply Stashed Changes**
    
    ```sh
    git stash apply
    ```
    Applies the most recently stashed changes.

21. **Remove Untracked Files**
    
    ```sh
    git clean -f
    ```
    Removes untracked files from the working directory.

### Viewing and Logging

22. **View Commit Logs**
    
    ```sh
    git log
    ```
    Displays commit logs.

23. **Show Changes**
    
    ```sh
    git diff
    ```
    Shows changes between commits, commit and working tree, etc.

24. **Show Specific Commit Changes**
    
    ```sh
    git show <commit>
    ```
    Displays changes in a specific commit.

### Configuration

25. **Set User Name**
    
    ```sh
    git config --global user.name "Your Name"
    ```
    Sets the name to be used with your commits.

26. **Set User Email**
    
    ```sh
    git config --global user.email "your.email@example.com"
    ```
    Sets the email to be used with your commits.

These commands cover a wide range of tasks from initializing repositories and managing branches to handling remote repositories and viewing logs.
