# A Beginner's Guide to Git, GitHub, and Visual Studio Code

## Overview
1. [How to use Git (Bash)](#how-to-use-git-bash)
2. [How to use GitHub](#how-to-use-github)
3. [How to use Visual Studio Code](#how-to-use-visual-studio-code)
4. [Glossary](#glossary)
6. [Sources](#sources)

## How to use Git (Bash)

### Install Git
Access the [git installer](https://git-scm.com/downloads) to download git on your respective device.

### Create a Repository
1. Open a terminal or command prompt.
2. Navigate to the folder where you want to initialize your project.
3. Run `git init` to create an empty Git repository.
4. Create or copy files into this folder.

### Remote Repositories
You can link your local repository to a remote repository like GitHub:
1. Create a repository on GitHub (instructions above).
2. In the terminal, link your local repository to GitHub using: `git remote add origin <repo url>`
3. Push your changes to GitHub using: `git push -u origin <branch>`

### Creat a Branch
1. Run `git checkout -b <branch-name>` to create and switch to a new branch.
2. Run `git checkout <branch-name>` to simply switch to an existing branch.

### Make and Commit Changes
1. Run `git add .` to stage your files for commit.
2. Run `git commit -m "<commit message>"` to save your changes in the Git history. This creates a local save.

### Open a Pull Request
Run `git merge <branch-name>` to merge changes from another branch into the current branch.

### Resolving Merge Conflicts
If Git encounters conflicting changes while merging, it will mark the affected files and stop the merge. To resolve:
1. Open the conflicting files and decide which changes to keep.
2. Edit the files to remove conflict markers `(<<<<, ====, >>>>)`.
3. Add and commit your changes using the add and commit commands mentioned earlier.


## How to use GitHub
The following with show you how to use GitHub and run git commands using GitHub's GUI.

### Create an Account
Create a GitHub account at [github.com](https://github.com/).

### Create a Repository
A repository as a folder that contains related items, such as files, images, videos, or even other folders. A repository usually groups together items that belong to the same "project" or thing you're working on.
1. In the upper-right corner of any page, select `+`, then click `New repository`.
2. In the "Repository name" box, type the repository name.
3. In the "Description" box, type a short description.
4. Select whether your repository will be `Public` or `Private`.
5. Select Add a README file. This is simply the front-facing file that displays information about your project.
6. Click `Create repository`.

### Create a Branch
Branching lets you have different versions of a repository at one time. The default branch is named `main`. When you create a branch off the main branch, you're making a copy, or snapshot, of `main` as it was at that point in time. If someone else made changes to the main branch while you were working on your branch, you could pull in those updates.
1. Click the `Code` tab of your repository.
2. Above the file list, click the dropdown menu that says `main`.
3. Type a branch name into the text box.
4. Click `Create branch`.

### Make and Commit Changes
1. Under the new branch you created, click any file. For example, the `README.md` file.
2. To edit the file, click the pencil button on the top right.
3. In the editor, write description of your project.
4. Click `Commit` changes.
5. In the "Commit changes" box, write a commit message that describes your changes.
6. Click `Commit changes`.
These changes will be made only to the `README.md` file on your new branch, so now this branch contains content that's different from `main`.

### Open a Pull Request
Pull requests show differences of the content from both branches.
1. Click the `Pull requests` tab of your repository.
2. Click `New pull request`.
3. In the Example Comparisons box, select the branch you made to compare with `main`.
4. Look over your changes in the `Compare` page.
5. Click `Create pull request`.
6. Give your pull request a title and write a brief description of your changes.
7. Click `Create pull request`.

### Merge a Pull Request
Merge your new branch into the main branch. After you merge your pull request, the changes on your new branch will be incorporated into `main`.\
<br />Sometimes, a pull request may introduce changes to code that conflict with the existing code on `main`. If there are any conflicts, GitHub will alert you about the conflicting code and prevent merging until the conflicts are resolved.
1. At the bottom of the pull request, click `Merge pull request` to merge the changes into `main`.
2. Click `Confirm merge`. You will receive a message that the request was successfully merged and the request was closed.
3. Yo have the option of deleting your old branch  by clicking `Delete branch`. If you want to make more changes to your project, you can always create a new branch and repeat this process.
4. Click back to the `Code` tab of your repository to see your published changes on main.

### Example Git Workflow
```
mkdir my-project
cd my-project
git init
git remote add origin https://github.com/your-username/my-project.git

git checkout -b feature-branch

git add .
git commit -m "add new feature"

git checkout main
git merge feature-branch

git push origin main
```


## How to use Visual Studio Code
Below is a breif explanation of how to use VScode for website applications development.

### Download VScode
VScode is a free code editor, which runs on the macOS, Linux, and Windows operating systems. Follow the platform-specific guides below:
- [macOS](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)
- [Windows](https://code.visualstudio.com/docs/setup/windows)

### Dowload Extensions
VScode offers extentions that add addition features to better enhance user experience. Below are a few extentions I use for web developement as well as general, all-purpose programming. They are not required but highly recommended.
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) - starts a local server that serves pages using files in the workspace and automatically reloads when an associated file is changed
- [ESLint](https://eslint.org/) - finds and fixes problems in your JavaScript code
- [Intellicode](https://learn.microsoft.com/en-us/visualstudio/ide/using-intellisense?view=vs-2022) - produces smart code completion recommendations that make sense in the current code context
- [Intellisense for CSS Class Names in HTML](https://marketplace.visualstudio.com/items?itemName=Zignd.html-css-class-completion) - provides code completion for the HTML **class** attribute from existing CSS definitions found in the current Visual Studio Code workspace
- [GitLens](https://www.gitkraken.com/gitlens?utm_source=gitlens-extension&utm_medium=in-app-links&utm_campaign=gitlens-logo-links) - offers the advantage of using Git source control within VScode
- [Prettier](https://prettier.io/) - automatically formats your code using consistent formatting rules

### Edit Files
Use the following commands to begin using the editor. Each will prompt you with a file explorer that will designate the location of the content.
- Create and open a new file with `File > New File...`.
- Open an existing file with `File > Open File...`.
- Open an existing directory with `File > Open Folder...`.

### View your files
There are serveral ways to view your files in a browser.\
<br/>First ensure that you have a `index.html` file. This will be the first page that will be loaded. Make sure your supporting files are correctly referenced by the index file.
- Double click on the index file. This will open the local version of your content on a browser. Refresh the page after making any changes to the code.
- Use the [Prettier](https://prettier.io/) by selecting `Go Live` at the bottom right of the window opening a browser. Changes will be automatically updated in the browser.
- Read below about how to serve your content publicly useing `Github Pages`.

### Using Git in VScode
Execute the following steps in order to use the git commands outlines in [How to use Git (Bash)](#how-to-use-git-(bash)).
1. Be sure to restart VScode after git is installed.
2. Open a new terminal in VScode by selecting `Terminal > New Terminal`.
3. Search "Default Profile".
4. Under `Terminal › Integrated › Default Profile`, select "Git Bash" from the dropdown.


## Glossary
**Branch** -  an isolated location for code and development that doesn't affect other branches in the repository\
**Clone** - create a local copy on your computer and sync between the two locations\
**Commit** - a snapshot of an entire repository at a specific time, recording changes to one or more files in a branch\
**Fetch** - retrieves new work done by other people and grabs all the new branches\
**GIT** - Git is a version control system that lets you manage and keep track of your source code history\
**Github** -  a developer platform that allows developers to create, store, manage and share their code\
**Merge** - a command that takes the independent lines of development created by branches and integrates them into a single branch\
**Merge Conflict** - happen when people make different changes to the same line of the same file, or when one person edits a file and another person deletes the same file\
**Push** - used to upload local repository content to a remote repository\
**Pull** - used to fetch and download content from a remote repository and immediately update the local repository\
**Remote** - repositories that are versions of your project that are hosted on the Internet or network somewhere
**Repository** - a virtual storage of your project


## Sources
- https://www.atlassian.com/git/tutorials
- https://docs.github.com
- https://git-scm.com/book
- https://code.visualstudio.com/docs
- https://medium.com/@gautammanak1/10-must-have-vscode-extensions-for-web-development-44b0d129ae56
