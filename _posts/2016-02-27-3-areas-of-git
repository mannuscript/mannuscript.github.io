This is blog 2 from series of blogs **Getting started with git.**

**Jargon to understand before going further:**
These are the terms related to git which I will be using often

* **Git**- A protocol which is distributed version control system.
* **Commit**- You commit a change i.e. you modify some file and store that change into version control system.
* **Repository(repo)** – The parent directory which is being version controlled by git.
* **Github** – git repository hosting service.
* **Clone** – When you download a repository from github or any other remote.


Git divides your whole bunch of code (repository) in 3 areas→

1. Git directory
2. Staging area 
3. Working area

Git directory is your committed code stored in the database of git in compressed form. Every commit you create gets stored into this place. It stores the whole history of code and this is something which is downloaded from github (or any other remote) when you clone a repository.

Working directory is the place where you work, it is the “latest snapshot” of the code fetched from git directory. All the files (untracked, tracked, modified) that you see in your repo are residing in working area.

![](/content/images/2016/02/Screenshot-from-2016-01-03-19-42-02.png)All the files we can see in our directory belongs to working area.


Staging area comes between git directory and working area, every change you commit has to pass through staging area.
When we create a commit, it takes staging area as the reference point. Only files which are staged will go to git directory.


**Workflow between areas:**

1. You load git directory when you clone a project from one of the remote.
2. Git fetches the latest snapshot of code from git directory and puts every file into your working area.
3.After modification you stage a file to commit it.
4. You commit your changes into git your directory.

![](/content/images/2016/03/1.png)
