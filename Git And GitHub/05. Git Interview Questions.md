**Here are 50 Git Interview Questions from basic to advanced along with their answers for DevOps Interviews:**

**Basic Git Interview Questions:**

1. What is Git?

   Git is a distributed version control system that tracks changes in files and coordinates work among multiple developers.

2. What are the key features of Git?

   Distributed version control
   
   Branching and merging
   
   Lightweight and fast
   
   Data integrity
   
   Staging area
   
   Collaboration support through remote repositories
   
3. How is Git different from other VCS like SVN?

   Git is distributed, while SVN is centralized.

   Git branches are lightweight, whereas SVN branches are heavy.
   
   Git provides faster performance compared to SVN.
   
4. What is a repository in Git?
   
   A repository (repo) is a directory that stores your project files and their version history.

5. What are the types of Git repositories?

   Local repository: Stored on your local machine.

   Remote repository: Stored on a server for collaboration.

6. How do you initialize a Git repository?
   
   Use git init to initialize a new repository in the current directory.

7. How to clone an existing repository?
   
   Use git clone <repository-url>.

8. What is the difference between Git pull and Git fetch?

   git fetch: Retrieves changes from the remote repository without merging them.
   
   git pull: Fetches and merges changes into your current branch.
   
9. How do you check the current Git status?
    
   Use git status to check the state of the working directory and staging area.

10. What is the purpose of the .gitignore file?
    
    It specifies files and directories that Git should ignore (e.g., build files, credentials).

11. How to add changes to the staging area?
    
    Use git add <file> or git add . to stage all changes.

12. How to commit changes in Git?

    Use git commit -m "commit message".

13. What is a branch in Git?

    A branch is a separate line of development within a repository.

14. How do you create a new branch?
    
    Use git branch <branch-name>.

15. How to switch to a different branch?

    Use git checkout <branch-name> or git switch <branch-name>.

16. What command merges two branches?

    Use git merge <branch-name> to merge a branch into the current branch.

17. How do you delete a branch locally?

    Use git branch -d <branch-name> or git branch -D <branch-name> to force delete.

18. How do you delete a remote branch?
    
    Use git push origin --delete <branch-name>.

19. What is the difference between merge and rebase?

    Merge: Combines branches, retaining their history.
    
    Rebase: Moves changes from one branch to another, creating a linear history.
    
20. How to see the commit history?

    Use git log.

21. What is the difference between git reset and git revert?

    git reset: Moves the HEAD to a previous commit, altering history.
    
    git revert: Creates a new commit to undo changes without altering history.
    
22. How to revert a specific commit?

    Use git revert <commit-hash>.

23. How to discard changes in a file before committing?

    Use git checkout -- <file>.

24. How to remove a file from Git tracking but keep it locally?

    Use git rm --cached <file>.

25. How to stash changes in Git?

    Use git stash.

26. How to apply stashed changes?

    Use git stash apply or git stash pop.

27. How to view remote repositories?
    
    Use git remote -v.

28. How to push changes to a remote repository?
    
    Use git push origin <branch-name>.

29. What is a detached HEAD in Git?
    
    A state where HEAD points to a specific commit instead of a branch.

30. How to rename a branch?

    Use git branch -m <new-branch-name>.

**Advanced Git Interview Questions:**

31. What is the difference between soft, mixed, and hard reset?

    Soft: Resets HEAD but keeps changes staged.

    Mixed: Resets HEAD and unstages changes.

    Hard: Resets HEAD and discards all changes.

32. What are Git submodules?
    
    Submodules are repositories within a repository, used for managing dependencies.

33. How to update a submodule?
    
    Use git submodule update --remote.

34. How does Git handle merge conflicts?

    Git marks the conflicting areas in files, and you resolve them manually.

35. What is the use of git cherry-pick?

    It applies a specific commit from one branch to another.

36. How to rebase interactively?

    Use git rebase -i <base-branch>.

37. What is Git bisect?
    
    It helps find the commit that introduced a bug using binary search.

38. What is Git reflog?

    Reflog records changes made to HEAD, including those not in the commit history.

39. How to remove the last commit without losing changes?
    
    Use git reset --soft HEAD~1.

40. How do you create an annotated tag?

    Use git tag -a <tag-name> -m "message".

41. What is the difference between annotated and lightweight tags?

    Annotated: Contains metadata (e.g., message, author).
    
    Lightweight: Simple pointer to a commit.
    
42. How do you force push changes?
    
    Use git push --force.

43. What is the significance of git config?
    
    It configures Git settings like username, email, and editor.

44. What is the purpose of the git fsck command?

    It checks the integrity of the repository.

45. How to squash commits in Git?
    
    Use git rebase -i and mark commits as "squash" (s).

46. What is the difference between git archive and git bundle?

    git archive: Creates a zip/tar of files.

    git bundle: Bundles repository data for transfer.

47. How to find a specific commit in the history?
    
    Use git log with filters like --grep or --author.

48. What is the difference between git stash pop and git stash apply?

    git stash pop: Applies changes and deletes the stash.
    
    git stash apply: Applies changes without deleting the stash.
    
49. How to set up tracking for a new remote branch?

    Use git branch --set-upstream-to=origin/<branch-name>.

50. How can you undo a merge?

    Use git reset --merge or git revert -m 1 <merge-commit-hash>.
