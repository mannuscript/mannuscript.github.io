This is part of series of blogs **Getting started with git**. Heretofore we were discussing the theory of git, now lets get started with git commands.

**git init**→ Initialize a directory with git. It is used when you have a directory of code which you want to start tracking with git.

![](/content/images/2016/03/Screenshot-from-2016-01-17-21-42-31.png)

As shown above, projectEuler directory was not tracked by git. (Error → fatal: Not a git repository or any of the parent directories: .git). But after ***git init***, ***git status*** shows you the list of un-tracked files, which signifies the initialization of a git repository and state of all the files that are un-tracked initially.
With close examination, you will notice a hidden ***.git*** directory, created by ***git init*** command. This is the directory which holds every single detail used by git like:

* Database of snapshots
* Tree object of git commits
* Local configs and so on.


***

**git remote add**→ Your newly generated repo has no remote (code hosting server) associated with it yet. To get a remote address, you need to visit your github/bitbucket profile and create a new repository.

![](/content/images/2016/03/Screenshot-from-2016-01-18-05-55-57.png)

As shown in the image you will get the remote url after creating the new repository.
Usage→ 
`git remote add origin https://github.com/mannu1200/projectEuler.git`
will create a remote for my project.


**git clone** → Allows you to clone a repository from remote to your machine. Git clone downloads the “git directory” from remote and creates a working area on your system by fetching latest snapshot from git directory.
Usage→ 

`git clone  https://github.com/mannu1200/projectEuler.git`


**git status**→ Apart from the current branch , it enlists the files which are in → staging area, un staged (Modified) and un tracked.

![](/content/images/2016/03/Screenshot-from-2016-01-30-22-46-42.png)

As shown in image, git status shows 3 types of files
q1.js is modified and added (Staged), ready to be committed.
q2.js is modified but not added (un-staged).
q31-coinSums.js is untracked, not present in git history.
Usage → `git status`


**git add** → git add command changes the state of your file from unstaged to staged(ready to be committed)
Usage → “git add filename” or “git add .” using . (dot) instead of the file name marks all the un staged and un committed files as staged.

**git commit** → Moves your files residing in staging area to git directory, creating the commit object, storing all the information like metadata, author data, commit message, parent pointer and all other information which we discussed in previous post of commits.
Usage → `git commit -m'my initial commit' ` 
-m is for appending commit message.

**git ignore** → git ignore is used to prevent files and directory from git versioning, if you want to store log files of your project, all you have to do is to add *.log in your gitignore file.
Git looks for a file with name .gitignore in parent directory of project.
A typical .gitignore file for a node.js project will contain →

    node_modules
    .project
    .settings
    logs
    npm-debug.log
    idea/


**git blame** → git blame is a very useful tool, it literally allows you to blame your colleague when code breaks :P. git blame provides you the power to see who and when committed the code in a particular file (in line wise fashion).


![](/content/images/2016/04/Screenshot-from-2016-04-15-21-48-16.png)


**git stash** → Think stash as an almirah or a stack, you put your unstaged (un tracked files are not included) changes of code in it, do some other required stuff like branch pull, branch checkout, branch merges etc and pop out from stash to your working directory.
For instance →

![](/content/images/2016/03/stash.png)

1. You made some changes in some files.
2. But then you realized your master branch might not be up to date with remote.
3.You stash those changes.
4. Take pull of your master branch.
5.Pull out from stash.
6.And continue with your other stuff.

Usage → 	
`git stash
git stash pop
git stash list (Enlist entries in stash, remember stash is a stack it can hold multiple values)`
		


**git pull:** git pull updates your git directory with remote. It fetches all the commits made by others and and stores it in your local git directory.
