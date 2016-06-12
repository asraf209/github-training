# GitHub for Developers, Day 2
Tuesday, May 17, 10AM-11AM

### Workflow Review Project: GitHub Games
**Fork and Pull Workflow**
- There are two types of accounts on GitHub: User and Organization
- We are forking (copying to our own accout) from the organization [GitHub School](https://github.com/githubschool)
- Navigate to [the github-games repository](https://github.com/githubschool/github-games)

**GitHub Pages**
- Every repository has the functionality to show a webpage through gh-pages.
- GitHub will display the version that exists on the branch `gh-pages`.
- These can be used to host personal sites, documentation, or projects. 
- You can see the page displayed at http://USERNAME.github.io/REPOSITORY

_Note: If you were working with the remote workspace yesterday, you will need to [download Git](https://git-scm.com) and set the configs on that machine._ 

**Fork the project**
- Fork the repository by clicking the `fork` button on the top right hand side of the browser view
- Navigate to your own fork of the repository. At the top of the page, it should say `your-user-name/github-games`, NOT `githubschool/github-games`
- In the code tab of your own repository, update the website to say your username instead of 'githubschool'. 
- CD into the directory where you want to clone your repository.
- Clone your repository to your local environment by copying the HTTPS link in your browser and typing `git clone <your-URL>` into your terminal.
- Type `cd github-pages` to enter the repository locally.

**Make local changes**
- Create a new branch and checkout to the branch at the same time by typing `git checkout -b readme-update`
- Edit the `readme.md` file with your text editor so the link on line 5 reflects your username instead of `githubschool`
- Save those changes, and exit the text editor
- Type `git status` to see your current branch and current stages of each file

**Share changes to GitHub**
- Type `git add readme.md` to move your files from working to staging
- Type `git commit -m "update link in readme"` to move files to history
- To push the changes to the remote repository in the correct branch to reflect your local branch, type `git push -u readme-update`.
- See your changes on GitHub.com! :tada: 
- Read more about remote branches [here](https://git-scm.com/book/ch3-5.html).

**Create your Pull Request**
- On GitHub.com, navigate to your own repository of githubgames.
- Click 'pull request'. Make sure the fork is your own copy for both comparisons, and  the 'Base: gh-pages' and 'Compare: shape-colors'.
- Click 'Create pull request'.
- Merge your pull request and delete the branch on GitHub.com. 

**Change the speed**
- Make sure our local repository is updated
  - Go to the top level branch: `git checkout gh-pages`
  - Update the local copy: `git pull`
  - See all of the branches on the remote: `git branch --all`
- Checkout to the stats-update branch: `git checkout stats-update`.
- Reverse merge the deployed branch, `gh-pages`, into the `stats-update` branch.
  - `git merge gh-pages`
  - **Merge conflict!** 
  - If you aren't ready to fix the conflict, you can get out of the merge with `git merge --abort`. 

**Fix the merge conflict**
- Open `inde.html` in your favorite text editor and look for the merge conflict markers. 
- Delete one copy of the code as well as the merge conflict markers. 
- Save and close.
- Type `git status` to see the current status of your files.
- Commit the changes: `git commit -m "Enter commit message"`.




# GitHub for Developers, Day 2
Tuesday, May 17, 1PM

### Continuing to fix the merge conflict
- Push up to GitHub: `git push`.
- On GitHub.com, create a new pull request between these two branches. Make sure you're comparing both branches of your own fork. 
- Merge the pull request and delete the branch.

**Change colors**
- Make sure our local repository is updated
  - Go to the top level branch: `git checkout gh-pages`
  - Update the local copy: `git pull`
  - See all of the branches on the remote: `git branch --all`
- Checkout to the shape-colors branch: `git checkout shape-colors`.
- Open `inde.html` locally.
- Around line 115, change the colors of the block. 
- Save the file and close your text editor.
- Add the changes: `git add -A`
- Commit the changes: `git commit -m "Enter your commit message here"`
- Send changes up to GitHub: `git push`

### Pull request for color changes
- On GitHub.com, navigate to your own repository of githubgames.
- Click 'pull request'. Make sure the fork is your own copy for both comparisons, and  the 'Base: gh-pages' and 'Compare: shape-colors'.
- Click 'Create pull request'.
- See that there's a merge conflict where normally there would be a big, green button.

### Resolve merge conflict from GitHub.com
- Following the steps about resolving a merge conflict on GitHub.com, you may notice you don't need to do all of these steps. 
- Update your remote: `git pull`
- We are going to do a 'reverse merge', merging the functional main branch into our feature branch to resolve the merge conflict.
- Merge changes locally: `git merge gh-pages`.
- Merge conflict! Open `inde.html` in your favorite text editor and look for the merge conflict markers. 
- Delete one copy of the code as well as the merge conflict markers. 
- Save and close.
- Type `git status` to see the current status of your files.
- Commit the changes: `git commit -m "Enter commit message"`.
- It came up in class that some users are having to log in every time they push - [read here about how to cache your credentials](https://help.github.com/articles/caching-your-github-password-in-git/).
- Push up to GitHub: `git push`.
- On GitHub.com, see that the merge conflict notification has been changed on the pull request. 
- Checkout back to our main branch: `git checkout gh-pages`
- Merge our changes with a recursive merge: `git merge --no-ff shape-colors`
- Push the changes up to GitHub: `git push`
- Go back to GitHub.com to see how the merge conflict has updated on the pull request. 
- Merge the pull request and delete the branch.

**Clean up the local environment**
- Make sure you have all of the remote tracking branches: `git pull --prune`
- See what branches are merged: `git branch --merged`
- Delete branches that have been merged: `git branch -d shape-colors stats-update`

### Reverting Commits
- `git revert` creates a new commit that is the exact opposite of the selected commit. This is important to note when thinking about impact on history!
- Revert a commit by typing `git revert <first-4-of-commit#>`.

### Fixing the broken game
- See the commit history: `git lol`.
- Find the commit where index.html was renamed to inde.html and copy the first 4 characters of that commit ID
- Revert that commit: `git revert <first-4-characters>`. (In this case, the first 4 characters are 2710, so we will type `git revert 2710`.)
- Complete the commit message in your text editor, save, and close.
- Push your local changes to the remote repository: `git push mygame`.
- See your working game by going to the new link in the README on your remote repository.



# GitHub for Developers, Day 2
Tuesday, May 17, 2:30PM

### New feature - practice `git mv` and `git add -p`
- Create a new branch and checkout to it: `git checkout -b slow down`
- Open index.html. We are going to change the speed in the index.html file, line 78.
- On line 78, change the speed to be slower (or faster if you'd like!)
- Save the file and close the text editor.
- See the status: `git status`
- Rename the file and move it to a directory: `git mv texture.jpg images/texture.jpg`
- Hunk the changes with a patch:
  - `git add -p`
  - `y`
  - `n`
  - `git status`
- Confirm changes with `git diff HEAD`
- `git diff --color-words HEAD`
- `git commit -m "enter commit message"`
- `git status`
- `git checkout gh-pages`
- `git merge slow-down`
- `git push`


### Practice rewriting history
- CD back into your preferred directory to create a new repository
- Create a new repository locally: `git init practice-repo`
- CD into that repository: `cd practice-repo`
- Create a README: `touch README.md`
- Add the readme to the repository: `git add README.md`
- Commit the readme: `git commit -m "init the repository with a README"`
- We are going to use empty files to practice rewriting history
  - Create four new files: `touch file1.md file2.md file3.md file4.md`
- Add and commit all of those files separately
  - `git add *1*`
  - `git commit -m "adding file 1"`
  - `git add *2*`
  - `git commit -m "adding file 2"`
  - `git add *3*`
  - `git commit -m "adding file 3"`
  - `git add *4*`
  - `git commit -m "adding file 4"`

#### Git Reset
- Find resource for `git reset` [here](https://services.github.com/kit/modules/CONT-CLI-19_Resetting-history.html)
- Be careful with `git reset` when pushing to a remote repository. Any time you push a commit, you should not use reset locally again. The commit ID will change, and that will alter their history in a possibly dangerous way.
- Three types of reset
  - `git reset --soft`
    - Commits will go into the staging area
  - `git reset --mixed`
    - Default behavior of `git reset`
    - Commits will go into the working directory
  - `git reset --hard`
    - Commits will be deleted

#### Practice `git reset --soft`
- See history: `git lol`
- Go back two commits: `git reset --soft HEAD~2`
  - See history now: `git lol`
  - Check status: `git status`
- Commit those changes: `git commit -m "adding files 3 and 4"`
  - Check status: `git status`
  - See history: `git lol`

#### Practice `git reset`/`git reset --mixed`
- Go back with `git reset <first-4-chars-of-commit-adding-file-2>`
  - Check status: `git status`
  - See history: `git lol`
- Re add those files
  -Re-add file 3: `git add *3*`
  -Re-commit file 3: `git commit -m "re-adding file 3"`
  -Re-add file 4: `git add *4*`
  -Re-commit file 4: `git commit -m "re-adding file 4"`
- Notice that the Commit ID is different than the first time those files were committed




#### Practice `git reset --hard`
- `git reset --hard <first-4-char-of-initalizing-repository>`
- This is a destructive command!
  - However, if you are _only_ working locally, you can rescue commits using `git reflog`.
  - `git reflog` does not stick around forever!
  - It only lasts for 90 days for a reachable commit.
  - Unreachable commits only last for 30 days.
  - These changes can be made in Git's configurations
  - The reflog is only local - nobody else with a copy of the repository will have access to your reflog.



### Git cherry-pick
- This command, `git cherry-pick` is not part of the every-day workflow
- `git cherry-pick` will bring back specific commits that may have been undone with `git reset` 
- It's also used to grab a single commit off of a feature branch and replay it on master.
- Practice by typing `git cherry-pick <commit-ID>` of a commit that has been undone
- It's important to only use `git cherry-pick` with commits that have not been pushed to a remote repository as it changes the commit ID of the same information

### Merge Strategies: Rebase
**About Rebase**
- The `rebase` command enables you to modify your commit history in a variety of ways.
- For today’s class, we’ll be using interactive rebase: `git rebase --interactive`, or git `rebase -i` for short.
- Because changing your commit history can make things difficult for everyone else using the repository, it’s considered bad practice to rebase commits you’ve already pushed to a repository.

**Get ready to practice Rebase**
- Type `git checkout -b rebase-me`
- Create 2-3 new files on your branch (HINT: you can use `touch file1.md file2.md file3.md`)
- `Add` and `commit` each file seperately.
- Type `git checkout master`
- Create 2-3 new files on master (e.g. `touch file4.md file5.md file6.md`)
- Take a look at your history by typing `git log --oneline --graph --decorate --all`

**Begin the Rebase**
- Type `git checkout rebase-me`
- Start the merge by typing `git rebase -i master`
- Your text editor will open, allowing you to see the commits to be rebased
- Save and close the `rebase-todo`
- Watch your rebase happen on the Command Line

**Check it Out**
- See your cool changes by typing `git log --oneline --graph --decorate --all`
- Go back to master by typing `git checkout master`
- Merge your changes in to master by typing `git merge rebase-me`






