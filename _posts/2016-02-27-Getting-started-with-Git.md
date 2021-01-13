Its only been 10 years since git has come into existence and it has already dominated the market of version control systems. All the famous startups are on git, Github is the portfolio of developers. Hence having basic understanding of git has become vital nowadays.

In this series of blogs, I will get you started with git, starting with the question **Why do we need git?** , this series will be helpful for those who are new to version control system as well as for those who are moving from other version control systems (like SVN) to git. I have tried to touch upon some in-depth topics about containment of git commits, which a novice may find uninteresting but my discourse would be incomplete without elucidating those mundane topics.

Before going deep into git, let us try to answer:

**Why do we need git ?**
To explain you this, I have a short story to tell. Story of a kid called Foo.

![](/content/images/2016/02/1-1.jpg)

Foo used to code his webserver in C++.  C++ being a compiled language, most of the bugs were found before deployment at his local machine. After completing the feature, he used to transfer his code using FTP tools like filezilla to his production server.
Things were going smoothly until one day when he switched to **NODE.JS**.
Dynamic, interpreted, loosely typed language, development became so fast. But then things started breaking at server.

![](/content/images/2016/02/2-2.jpg)

He started having many production bugs and higher downtime. Code which were running at local environment were breaking at production.

And then he realized the need of version control system (VCS). So that if some release breaks, he can easily switch back to later version of code.

![](/content/images/2016/02/3-2.jpg)
A **version control system** keeps the track of whole history of code. Your every change (commit) is stored as a new version, and you can easily switch between these versions. So if Foo finds out that his latest version 1.3 is breaking at production he will immediately revert to v1.2 and will later fix the bugs in v1.3.


With a VCS his life was back on track, he installed a VCS on his machine and started sending desired version to production through filezilla.

**Git is a VCS.**


Then one day Foo's friend Bar came to him and showed the desire to work with him on his node web-server. Upon which Foo immediately agreed.


Now the problem they were facing was to keep each other's code in sync at some common place, so that both can work simultaneously on the project. Hence they realized they require a **centralized versions control system (CVCS)** or a **distributed version control system (DVCS)**, which will keep their code in sync at some code hosting server/remote (such as github). Now the primary source of code will not be Foo's or any other's local machine and production's code will be updated through this remote server.
![](/content/images/2016/02/4-1.jpg)
CVCS and DVCS are two types of version control system which allow you to host your code at some code hosting server like github. CVCS and DVCS work on completely different ideology. Let us discern the difference between them in next blog and further dwelling deep into properties of git.
