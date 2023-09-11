




# What is Git?
[**Git**](https://git-scm.com) is a distributed version control system that allows a developer to track changes made to files in their projects. Teams of developers can use Git to collaborate on a single project at scale. This is made possible by branching, which allows developers to make specific changes to eventually be merged into the `main` branch of the codebase (or Git repository).

In simpler terms,
> Git is like a time machine for your development work, letting you save different versions of your projects and work on them with friends without messing things up. It's a tool that helps you keep track of changes and work together smoothly.

# Basic Terminology

###  repository (repo)
- When working on a project with collaborators, a Git repository acts as a special folder on your computer that records all the changes you make to your files. 
- This makes it simple to see what everyone has done and combine your work. It resembles a computerized version of journal that records everything you and your collaborators write in it.

### branch
- A branch in Git is comparable to a different project route. Similar to how you may write two different stories in various notebooks, it enables you to work on different aspects of your project without interfering with the primary one. 
- Conventional name for the primary branch of a project is `main`.

![Illustration to explain branches](https://rogerdudler.github.io/git-guide/img/branches.png)

### HEAD
- Think of the "HEAD" in Git as a special marker that, like a bookmark in a book, indicates which version of your project you are currently viewing. It aids in keeping track of your progress throughout the course of your assignment.
- HEAD is a reference variable used to denote the most current commit of the repository in which you are working. When you add a new commit, HEAD will then become that new commit.

### Index
- The **index** in Git is like a waiting area for your changes. When you make changes to your files, Git puts them in this waiting area until you're ready to save them. 
- When you run "git status," it shows you which changes are ready to be saved in green and which ones still need to be prepared in red.

### Remote
- Git remote is similar to a link to a shared copy of your code (repository) on the internet or another machine. It allows you and your collaborators to work on the same code from multiple locations, ensuring that everyone has the most recent modifications.
- A remote in Git is **a common repository that all team members use to exchange their changes**.

### Upstream/Downstream
- When talking about a branch or a fork, the primary branch on the original repository is often referred to as the `upstream`, since that is the main place that other changes will come in from. The branch/fork you are working on is then called the `downstream`. Also called origin.
- In Git, `upstream` refers to the original source of a project or repository. It's like saying, **Where the project started from,** and it helps you keep your work synchronized with the latest updates from that starting point.

### Workflow
- Your local repository consists of three `trees` maintained by **git**. 
- The first one is your `Working Directory` which holds the actual files. 
- The second one is the `Index` which acts as a staging area.
- Finally the `HEAD` which points to the last commit you've made.
	
![](https://rogerdudler.github.io/git-guide/img/trees.png)

# Tutorial
## Setup

- If you are using git for the first time, you will need to set up your identity. 
- Your identity 
You can do the same by using the following commands:

```bash
	$ git config --global user.name "Your Name"
	$ git config --global user.email youremail@example.com
```

- Setting up a Git identity using your name and email is crucial because it links your commits to your personal identifier, allowing you to claim credit for your work and facilitating teamwork. 
- In a Git repository, it aids in maintaining a transparent and verifiable history of modifications, which is essential for teamwork and accountability in software development.

## Cloning

In this tutorial, we will be working on this repo. So, how do you plan to import the code from here on Github onto your local machine?

1. Fork this repository on Github. You can find the fork button at the top right of the screen on a github repository, or more help about doing that [here](https://help.github.com/articles/fork-a-repo/).

![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSf_tbV9KvFZ16h4WOT_LRLq87Ozx73z9gPXVMFZQGL_mVkuB1zHdeo4H50oP5I4_fhKg&usqp=CAU)

2. Once you have forked this repository, you can clone it to your local machine. This will create a folder named `git-gud` and download all the files to your current working directory. You can clone using the following command:

```bash
	$ git clone https://github.com/<your_github_id>/git-gud.git  
```

3. Once you have cloned this repository, you can view the files by using the following commands:

```bash
	$ cd git-gud
	$ ls
```

This will change the working directory to be `git-gud`. The `ls` command will display the files in the current working directory. 

## Committing

Once you make a change to the `noughts-crosses.md` file, you want to commit your changes in order to save your changes in git. In order to commit you can use the following command:
```bash
	$ git commit  -m "placed an O/X on position 2x2"
```

> The `-m` flag allows you to enter a message to go with the commit at the same time. You can use -m to give a description of the commit you are making. It is generally used to summarize the changes made in the commit.

## Logging and Difference

> Do you want to revert the game to a previous stage, but aren't sure what was the state of the board at each stage? 

In order to view the commits you have made you can use the `git log` command. 

```bash
	$ git log
```

The log displays every commit ordered by most recent to least recent date. You would see a variety of information, including the message for the commit, the author's name, the date it was committed, and a commit SHA number.

However, we should notice that the `git log`  command does not display the changes itself. So, we can use the `git diff` command to display the changes between two commits or branches.

```bash
	$ git diff
```

## Pushing code

> Now, you have made changes and saved them as well. How do you share them with your partner?

In order to give your version of the board to your partner, we will upload/**push** your board to an online repository such as Github. We can do this by using the following command: 

```bash
	$ git push origin main
```

## Undoing changes

> You made the wrong move! Your partner is about to end the game... but you choose to use your revert move!

In order to move to a previous commit, we can use the `git checkout` command.    It will revert the changes on your local machine back to the requested commit SHA.

```bash
	$ git checkout <commit_id>
```

**However, this won't update in the Github repository.**

If you want to push these changes to the remote repository on Github, you can use the following command for the same: 

```bash
	$ git push origin main
```

# Git Commands

### git add
-  The `git add` command in Git is equivalent to saying to Git, "Hey, I want to save these changes!" when you make changes to your project. 
- For instance, if you repaired a bug in your code and wish to save it, you would tell Git to include that particular modification in your subsequent save (commit) by using the command 
```bash
	$ git add <filename>
```
### git commit
- Like taking a snapshot of your code at a particular moment in time, a "git commit" is a change. It's a technique to preserve your modifications and provide a brief note about what you changed. 
- For example, you might use it like this: 
```bash
	$ git commit -m "Fixed a bug in the game's scoring system."
``` 
to save your recent code changes and let others know what you did.

### git push
- `git push` is similar to posting your most recent code and modifications to a public online repository so that you and your team members can view and edit the same version.
- For example, if you want to share your cool game code with others, you'd use "git push" like this: 
```bash
	$ git push origin main
``` 

### git clone
- This command is used for making a copy of a project from the internet to your computer.
- For example, you can use it to copy a project from a website like this:
```bash
	$ git clone https://example.com/game.git
```
### git fetch
- `git fetch` is similar to checking for game updates. It doesn't alter your game; it just downloads the most recent updates from the internet to your computer so you can see what's new.
- You can use `git fetch` to see if there are any new levels or features in the game you're working on, but it won't actually change your game until you decide to use `git merge` or `git pull` to apply those updates.
	
### git merge
- Git merge is similar to merging two distinct code branches into one. 
- Use `git merge feature-branch` to combine two branches, such as when adding new characters to your game, if you have a branch for adding new features to a game called **feature-branch** and you want to integrate those features to the main game.

### git pull
- Imagine you have a project, and you want to make sure you have the latest updates from your collaborators. You can use `git pull` to get those updates: 
-  You can use `git pull` to fetch and merge remote changes.
```bash
	$ git pull origin main
```
  
### git remote
- In Git, a `remote` is like a bookmark that helps you remember the web address of a project you're working on. 
- For example, if you're collaborating on a game project, you might add a remote called "origin" like this: 
```bash
	$ git remote add origin https://github.com/username/game.git
```  
Then, you can use `origin` as a shortcut to refer to that web address when you need to push or pull changes.

### git checkout
- `git checkout` is like switching to a different branch or version of your project. 
- For example, if you have a branch called "feature" and want to work on it, you can use 
```bash
	$ git checkout feature
```
 - This will take you to that particular area of your project, where you can make modifications specifically for that feature.

### git branch
- The `git branch` command in Git is like making a list of different versions or "branches" of your project. 
- For example, if you're working on a game, you can use `git branch` to create a new branch called `bug-fixes` to work on fixing game bugs separately from the main version: 
```bash
	$ git branch bug-fixes
```
### git diff
- You can use the `git diff` tool to compare two branches in your Git project and observe their differences.   
```bash 
	$ git diff main feature
``` 
- For instance, to examine what changes you've made while comparing a branch called "feature" to the "main" branch you can use the above command. This command will clearly outline any new code or modifications to existing code that separate those two branches.

### git log

- `git log` is a command in Git that shows a detailed list of all the changes, or "commits," that have been made in a project. 
- It displays information like who made each commit, when they made it, and a unique identifier for each commit, which helps you keep track of the project's history. For example, running `git log` might show you a list of commits like this:

### git reset

- `git reset` rewinds your repository’s history all the way back to the specified unique ID. It’s as if those commits never happened. 
- By default, `git reset` preserves the working directory. The commits are gone, but the _contents_ are still on your computer. 
- This is the safest option, but often, you’ll want to “undo” the commits _and_ the changes in one move—that’s what `--hard` does.

Commands:
```bash
	$ git reset <unique_ID>
	$ git reset --hard <unique_ID>
```

### git reflog
- You made some commits, did a `git reset --hard` to “undo” those changes (see above), and _then_ realized: you want those changes back!
- `git reflog`  is an amazing resource for recovering project history. You can recover  _almost_  anything—anything you’ve committed—via the reflog.
- You’re probably familiar with the  `git log`  command, which shows a list of commits.  `git reflog`  is similar, but instead shows a list of times when  `HEAD`  changed.

![](https://github.blog/wp-content/uploads/2015/06/f6b9f054-d891-11e4-8c53-838eff9f40ae.png?resize=1429%2C644)

### git rebase
- `git rebase` is similar to changing the timeframe of your code. It makes your branch appear as though it was freshly created by moving your changes to the most recent point on the main branch rather than stacking them on top of it. 
- For example, if you have a branch called "feature" and you want to rebase it onto the latest changes in the "main" branch, you can run: 
```bash
	$ git rebase main
```
![A visualization to explain how rebase works](https://miro.medium.com/v2/resize:fit:1400/0*1VkO0oTn-PPPzJmx.gif)

### git revert
- While resetting works great for local branches on your own machine, its method of "rewriting history" doesn't work for remote branches that others are using.
- To reverse changes and  _share_  those reversed changes with others, we need to use  `git revert`.
- For instance, if you want to undo the changes from the last commit with the ID `abcdef`, you can use the below command to create a new commit that undoes those changes while keeping the commit history intact.
```bash 
	$ git revert abcdef
``` 

# Popular Issues

Here are some common error messages you may hit, and ways you can resolve them. If you run into something that isn’t here, please post an issue to the repo, and we’ll try to post up a solution ASAP

# Additional Resources

-  [Atlassian’s Guide to Git](https://atlassian.com/git/tutorials)
- [The Simple Guide to git](https://rogerdudler.github.io/git-guide/)
- [Learn Git Branching Visualization](https://learngitbranching.js.org/?locale=en_US)
- [How to undo (almost) anything with git](https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/)

# Contributing

Do you know any commands or terminologies that we haven't mentioned? Feel free to follow the steps below to add them!

1.  Fork it
2.  Clone it  `git clone <url of your forked repo>`
3.  Make branch  `git checkout -b <branch name>`
4.  Make your changes in `README.md`
5.  Add changes  `git add README.md`
6.  Commit changes  `git commit -m "subject line" -m "description"`
7.  Push changes to repo  `git push origin <branch you made>`
8.  Click `Compare & pull request`

## Credits
- Avaneesh Kumar - [Github](https://github.com/avaneeshk098)
