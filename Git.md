
Git is a version distributed version controlled system that enables multiple users to collaborate on projects, tracking changes in files and directories while providing a history of snapshots and the ability to manage different branches and merge code changes efficiently. 

==Why is Git important?==

1. Git is a standard tool for tracking and managing changes in software projects
2. Helps maintain a detailed history of code changes
3. Git integrates with CI/CD and other tools like Jenkins.

==Version Control==
1. Git is a version control system that is a standard stool for managing software projects

Centralised (SVN) vs Distributed (Git)

- SVN - everyone worked off a single central server. if the server went down you could not commit/do anything.
- lock files but you will end up in merge conflict file.
- Git - instead of relying on one server every developer has a full copy of the repo
- 

![[Screenshot 2025-06-24 at 00.22.49.png]]




==Merge Conflicts==

- When you do not do a GIT pull after a merge request your local machine is not up to date with remote repository. Then you will branch off to a version of the code which is older. 
- Occurs when Git cannot reconcile difference between two commits and requires manual resolution. 

git branch branchname
git checkout branchname 
git add README.md
git commit -m



==Gitignore==

