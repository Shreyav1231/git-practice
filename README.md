# Shreya's personal guide to Git

## Version control using git 

1. To add version control to an existing local directory -
   ``` git init ```
   This directory will now become a git directory, allowing you to use git commands to ensure version control.

3. The .git directory contains many important files like config, which stores the configuration settings like name, email, etc.
   Sometimes you may want to change your git username/email by doing.
   ```
   $ git config --global user.email "example@example.com"
   $ git config --global user.name "Example Name"
   ```
   If you want to change your username and email only for the current repository, you can omit the --global keyword.

4. ``` git status ``` lets you see the status of your repository. If a file is untracked, it means that file is not being followed by git and you should add it to the stream using ``` git add . ```.
5. ``` git log ``` lets you see all the commits you have made till date. The topmost being the most recent.

### Branches 
Let's say you are creating an app on the main branch, you want to test a new feature and so you create a new file. However, you don't want to disrupt the current code, you just want to test the new feature independently. This is when you use branches.
1. To create a branch - ``` git branch branch-name ```
2. To view all branches - ``` git branch -a ```
3. To go to your branch - ``` git checkout branch-name ``` (the branch you are currently on is green with an astrisk)
You can start working on your new feature in the branch. You can add and commit your changes. <br />
Note that branches are independent of each other after the splitting point. But the branch will still inherit files from the main branch. <br />

4. If you want to delete the branch but haven't merged it yet, run ``` git branch -D branch-name ``` from the main branch. If merged and want to delete the branch, run ``` git branch -D branch-name ```

### Merges
If you want to merge your feature branches into the main branch you should be on the main branch. Run ``` git checkout main ``` <br/>
1. Run ``` git merge branch-name ``` to merge branch-name into the main branch.

### Merge conflicts 
Let's say colleague A was working on the html file on main and made some changes to it. Colleague B worked on the same html file and made some changes (as previously mentioned, files get inherited from main to the branches). This leads to a merge conflict. <br/>
When colleague B merge the branch into the main branch, it raises a merge conflict. Merge conflicts are fixed in the main branch by specifying which changes the developer wants to accept.

### Staging 
Remember that when we run git status we can see 3 types of messages
1. To be committed - This means that the files have been staged and will be included in your next commit.
2. Not staged for commit - This means git is aware of the changes in your files, but they will not be included in the next commit.
3. Untracked - Git is not aware of these files. <br/>
``` git add ``` moves files to the staging area 

If you accidentally staged a file that you don't want to commit, you can run restore. However, here are a few notes to take before you do that. 

1. ``` git restore ``` DISCARDS unstaged changes in a partially staged file.
2. ``` git restore --staged filename-to-remove-from-stage ``` removes the file you didn't want to the stage from the stage. Unstaged changes are not deleted, it simply gets unstaged. The file now becomes untracked.
3. ``` git restore --worktree --staged file-name ``` discards both staged and unstaged changes. It will use the last committed version of the file.

## Working with multiple developers on the same project
To build on another developer's project 
1. Copy the project (Fork)
2. Make desired changes to the code
3. Request the owner to update the code base (Pull Request)
4. The owner can merge the pull request <br/>

Forking vs Branching - <br />
fork when you want to create an independent project, contribute to open-source projects, or experiment with significant changes in the project that might not be accepted by the original project.
When you need to work on a new feature or bug fix without disrupting the main codebase, you should branch.


## Sharing your repository with Github

Ensure you have gh installed using your preferred package manager

1. To create a repo on Github - ``` gh repo create ```
2. Ensure you add a remote origin and push
Note that now when you run ``` git log ```, you will see something like ``` commit abcdef12345 (HEAD -> main, origin/main) ``` which means your local main is exactly in sync with the remote origin/main.


## Magical Tips - 
1. Go back one commit ```git reset --hard HEAD~1```
