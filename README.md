# Git Cheatsheet

```bash
# To view hidden files too in directory
ls -la

# To init a local git repo
git init

# To see commit status
git status

# . period is to track all files
git add .

# Or specify the files e.g. index.html
git add index.html

# To see all branches (curr branch we will tagged by *)
git branch

# To rename the current branch e.g. to main
git branch -M main

# To create a new branch
git checkout -b feature_branch

# To switch branch (e.g. to main)
git checkout main

# To commit locally
git commit -m "Added index.html" -m "Some Description"

# To view all remotes
git remote -v
```

Now to push:

1. To push to an empty remote repository, after adds and commits

   Note that `origin` is the standard naming convention of the remote repository ID we are linking to. We can even add multiple remotes.

   ```bash
   # Adding the remote repository with an ID called origin
   git remote add origin https://github.com/Samthesimpsons/git-demo.git

   # Rename the current default branch name of master to main
   git branch -M main

   # Push to remote repository the local main branch
   # -u sets upstream, such that in the future we will push to the origin main just by saying git push
   # The remote repository branch name will be called main too
   git push -u origin main
   ```

2. If we cloned from a remote repository and want to commit from our local machine for the first time, after adds and commits

   ```bash
   # Since we cloned from the remote repository, the remote with the default naming convention of origin is setup
   # Hence all we need to do is just set the upstream for easier future pushes from main to origin/main
   # The local repository branch name will be called main since the remote repository branch we cloned from is called main too
   git push -u origin main
   ```

If we created a new feature branch and edited files on, add and commit there. Now if we switch back to main branch, the changes are not there.

1. ```bash
   # Assuming feature branch name is feature_branch
   # Note the -u to set a new upstream
   git push -u origin feature_branch
   ```

   Then accordingly do a pull request on github, merge and delete if needed. If we delete the branch on remote repository, good practise to also remove locally.

    ``` bash
    git branch -d feature_branch

    git checkout main

    git pull
    ```