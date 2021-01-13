**Snapshots not pointers**

Before understanding the structure of git commits, let us know how differently git stores its data compared to other VCS.

Other VCS like CVN, stores differential of changes of respective files.
![](/content/images/2016/03/snapshot1.png)

As shown in the figure, only the delta/changes in the files are stored between new commits, this is how size of commits are kept smaller and network calls of switching between versions are not data expensive.
On the contrary, Git follows completely different ideology.
Instead of changes/deltas, Git stores whole set of new files which have been changed. And this behavior leads to larger size of commits compared to other VCS.

![](/content/images/2016/03/snpashots.png)

Image shows how whole new files are being saved instead of just changes.

One may wonder how even larger size of git commits makes it faster than other VCS.
This doubt can be solved by understanding some basics as follows:

* Git is a DVCS, you have whole history of code in your local machine. Large size of commits causes expensive network calls for operations like pull/fetch/clone, however such operations are required rarely compared to operations like 'git diff' or any other operation which requires to compare the previous versions of code.

* Finding differential between two files is mere diff versionN.file1 versionM.file1 (like linux diff command), whereas when delta/changes are being saved instead of whole snapshots, the whole file has to be re-created to find the differential. The same thing goes while creating the commit tree.

Coming back to the central topic, let us learn about git commits.

Every time you run `git commit` git creates following objects: 

* **Blob object** → For every file which is in staging area, git creates a blob object to store it's data.
* **Tree object** → A tree object stores the information of all blobs.
It should be noted that tree object is not to be confused with commit tree(or git tree), commit tree is something which represent version control of git as a whole.
* **Commit object** → Commit object is something which represents a git commit, hence contains all the meta data (commit message, author, committer, date) +  pointer to the tree + parent commit pointer(s) (=<0).
 
Below image shows how these three object are connected with each other. 
![](/content/images/2016/03/tree.png)

Commits are connected with each other through a property called **parent**, which is a pointer storing the address of its previous commit.
A commit can have 0 or more parents pointers:
 
* 0 in case of root commit (1st commit of your code)
* 1 when it is a normal commit and 
* More than 1 when it is merge(merging of two branches) commit. 

![](/content/images/2016/03/commits.png)

Figure shows how a singly linked list is created from commits.
