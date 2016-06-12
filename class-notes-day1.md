# GitHub for Developers, Day 1
Monday, May 16, 10AM-12PM

### Getting Ready for Class
- Make sure you have [Git insalled](https://git-scm.com/) on your computer and a [GitHub account](https://github.com/). Your email will need to be verified to be a collaborator, so make sure you keep an eye on your inbox. :eyes: 

### Getting Started
- Repository for Class: https://github.com/githubteacher/developers-may-2016
- Tour of Repository: 
  - Code View:  Files belonging to the project
  - README.md: Description of the Repository 
  - Issues: A place to have conversations and collaborate
  - Pull requests: A place to collaborate while introducing changes to your project
- Comment on [this issue](https://github.com/githubteacher/devs-may-2016/issues/2) to become a collaborator on the project
- Practice making an issue [in the issues tab of the class repository](https://github.com/githubteacher/devs-may-2016/issues).
  - For today's activity, be sure to include your username in the title, like "YourUserName Hometown"
  - In the body of the issue, teams usually discuss things like adding a feature, fixing a bug, or making plans for something. 
  - You can include [markdown](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf) syntax here.

**Notifications**
- Notifications are an important part of GitHub. You can customize these several ways.
  - For GitHub in general, [Settings/notificatons](https://github.com/settings/notifications)
  - For repositories, at the top of a repository page on GitHub.com by clicking "Watch"
  - For individual issues and pull requests by clicking "unsubscribe" on the right hand side of the webpage
- On the pull request page, we talked about the different tabs for 'conversation', 'commits', and 'files changed'.
  - 'Conversation' is where you and your colleagues can collaborate on your changes. This view includes comments as well as notes of when changes happen.
  - 'Commits' shows a history of what commits were added - this is why your commit messages matter - they tell a story.
  - 'Files changed' will let you see the actual code in several different formats. You also can make line level comments from this view.

**Getting access to the collaborator script:**
The collaborator script is open-source! You can access it [here](https://github.com/github/training-utils). Our [training kit](https://github.com/github/training-kit) is also open-source. We invite you to use these and welcome contributions to both these repos!

### GitHub Flow
**You can find that visual of the GitHub flow at this link:** https://guides.github.com/introduction/flow/

### Branching with Git
**Review of branches**
- When you create a branch, you are essentially creating an identical copy of the project at that point in time that is completely separate from the master branch.
- Create a branch on GitHub.com in the class repository
  - Click the 'branch' dropdown 
  - Enter a branchname name 'username-recommends'

### Create a file on GitHub.com
- Make sure you are working on your own branch. You should see your branch name in the top left side. If you see 'master', you are **not** on your branch. 
- Click the grey button that says 'Create new file'. 
- Name the file `username-hometown` and include some recommendations for where @crichID and myself (@brianamarie) can eat and see new things! 
- Commit the file to your own branch. Make sure you include a short and descriptive commit message - commit messages are important! 

### Create a pull request
- Find the 'Pull requests' tab. Click the green button to create a new pull request.
- Make sure the branches are 'Base: master' and 'Compare: YOUR-BRANCH'. 
- Create a pull request. Give it a descriptive title and message. :pencil2: 
- **Note:** All teams have different protocol when it comes to merging pull requests. For today and this class, we will always merge our own pull requests. _However_, don't do it just yet. :wink: 
- Comment on someone else's pull request. You can post general comments, or line comments. Feel free to explore the views: conversation, commits, and files changed. 

### Edit on GitHub
- To edit a pull request file, you use the `files changed` view and click the `edit` icon.
- Once you've made changes, create a new commit on the bottom of the page. 
- Make sure you commit to the correct branch

----
Lunch break! :hamburger: 



# GitHub for Developers, Day 1
Monday, May 16, 1PM

### Local Git Configs
**Review of configurations:**
- We determined our git version by running `git --version`... version 1.9+ is recommended
- If you need to, you can install it [here](https://git-scm.com/)
- If you don't already have GitHub Desktop, you can install it [here](https://desktop.github.com/)
- Set up your Git configurations by running these commands:
  - `git config --global user.name "your name"`
  - `git config --global user.email <youremail@email.com>`
  - `git config --global core.editor <editor>` (For more help associating your text editor with Git, read [this GitHub Help article](https://help.github.com/articles/associating-text-editors-with-git/).
  - `git config --global push.default simple`
  - Windows ONLY: `git config --global core.autocrlf true`
  - Mac and Linux ONLY: `git config --global core.autocrlf input`
- Check your configurations by running `git config --list`

### Clone locally
- Clone the repository by running `git clone https://github.com/githubteacher/devs-may-2016.git` (Make sure you are in the directory where you want the repository to be when you run this command)
- If you get an error, set up a proxy using [these instructions](https://github.com/githubteacher/devs-may-2016/issues/40) set up by @dfstestmatt :tada:

### Working locally
- Checkout to the new repository using Git Bash.
- See all of the branches in the repository: `git branch -al` 
- Checkout to the branch you created earlier: `git checkout YOUR-BRANCH-NAME`
- List the files in your current directory by running `ls -la`
- Open the file that you created on GitHub locally in your favorite text editor. Make some changes, save, and exit the text editor.


### Committing changes
- Learn about 'working', 'staging', and 'history' and how commits fit into those areas using [this resource](https://services.github.com/kit/modules/CONT-CLI-04_Two_Stage_Commit.html).
- See your working/staged area  `git status`. This command is :heart:! 
 
   1. Change your file from 'working' to 'staging' by running `git add <file-name>`
   2. Change your file from 'staging' to 'history' by running `git commit`
   3. Text editor opens: Write a 'commit message' tells a story of the changes you just made in 50 characters or less.

- Here are some shortcuts to know about in the future:
  - To automatically stage all files that have been changed, run `git add -A`. Note: This will only work for files that are already being tracked, not brand new files.
  - Avoid the text editor in the commit by running `git commit -m "commit message"`




# GitHub for Developers, Day 1
Monday, May 16, 2:30 PM

### Move your commits to the remote repository
- After adding and committing files, you can update the remote repository with your changes.
- Since we created the branch on GitHub.com and checked out to it locally, all we need to do is `git push`. :tada:

### Merging Pull Requests
- During class, please do not close or merge any pull requests other than your own.
- On your own pull request, if all is green and there are no conflicts, go ahead and merge your branch.
- After merging a branch, it's part of the `master` branch and good practice is to delete it.
  - This is a major difference between Git and some older version control systems. In Git, branch often, merge often, and delete branches often.
- Back at the command line, we need to pull down the changes from GitHub.com in the remote repository.
   - `git checkout master`
   - `git pull`
   - `git branch --merged`
   - `git branch -d <branch-name>`
   - `git fetch --prune`
- Configure your settings to do this by default by typing `git config --global fetch.prune true`

### Local History
- Use `git log` to view the history of the repository
- `git log` will show commits from your own local repository, but also changes made by other collaborators 
- Experiment with different option switches to view history:
  - `git log`
  - `git log --oneline`
  - `git log --oneline --graph`
  - `git log --oneline --graph --decorate`
  - `git log --oneline --graph --decorate --all`
  - `git log --stat`
  - `git log --patch`
- Use the up and down arrows or press enter to view additional log entries. Type q to quit viewing the log and return to the command prompt.

### Streamline Workflow With Aliases
- Set up an alias in configurations: `git config --global alias.<desired-alias> "the long version of the command that you want the alias to run, without git at the beginning, and with the desired flags"`
- Cynthia's alias is: `git config --global alias.lol "log --oneline --graph --decorate --all"`


### View Local Changes
- View local diff diagram [here](https://services.github.com/kit/modules/CONT-CLI-11_Viewing-local-diffs.html)
- `git diff`: See local changes between working, staging, and history
- If we have added more changes to a file that we've already created, we can see differences between them with `git diff`
- Add to the file you've been working on. 
- See status: `git status`
- Create a new branch, and checkout to that branch: `git checkout -b USERNAME-more`. When you do this, the modified file will move to the branch from master. There's only one working directory, regardless of the number of directories. 
- Stage the file: `git add -A`.
- See status: `git status`.
- Open the file again, and make another change. Save the file. 
- See status: `git status`.
- See differences with `git diff`.
  - `git diff`
  - `git diff --staged`
  - `git diff HEAD`
- `git commit -m "commit message"`
- Make another change.
- Stage: `git add .`
- See status: `git status`.
- See differences with `git diff`
  - `git diff`
  - `git diff --staged`
  - `git diff HEAD`
- There's a commands that functions as both the 'add' and 'commit': `git commit -a -m "enter commit message here"` 

### Fixing Commit Mistakes
- Change a commit message with `git commit --amend`


