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
I used to struggle with branches a lot before. Hopefully this makes it simpler.
Let's say you are creating an app on the main branch, you want to test a new feature and so you create a new file. However, you don't want to disrupt the current code, you just want to test the new feature independently. This is when you use branches.
To create a branch - ``` git branch branch-name ```
To view all branches - ``` git branch -a ```
To go to your branch - ``` git checkout branch-name ``` (the branch you are currently on is green with an astrisk)
On your branch, you will see files from the main branch and can add your own stuff
It's amazing to note that branches are independent of each other after the splitting point. But the branch will have data from the main ba
## Sharing your repository with Github

Ensure you have gh installed using your preferred package manager

1. To create a repo on Github - ``` gh repo create ```
2. Ensure you add a remote origin and push
Note that now when you run ``` git log ```, you will see something like ``` commit abcdef12345 (HEAD -> main, origin/main) ``` which means your local main is exactly in sync with the remote origin/main.


TBC
