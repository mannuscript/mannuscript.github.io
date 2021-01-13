Git config is something which lets you get and set configuration variables controlling all aspects of appearance and operation of git. Configs like username, email id, editor, remote and so on comes under git config.

There are 3 levels of git configs →
**1. Local config:**
Local configs are applied to a single repo for which configs have been set. They have been saved to .git/config file. Remote details of a repo are always stored in local config.
To enlist your local config run → **git config --local --list**

**2.Global config:**
Global configs are (use same form everywhere) applied to your user on the machine. They will be applied to all the repository cloned/created by your user and is ideal for storing default editors (vim), user details like email/name and so on.
Enlist them using → **git config –global --list**

**3.System config:**
System configs are applied to every user on the machine, every repository created/cloned on the machine irrespective of user.
**git config --system --list (it may result in an error if you have not set any yet)**
	

Local configs override global configs which further override system's. Hence setting your private email id in the local config of your private repo, when you have already set your official email id in your global config, will work.

**To view config of given level:** 
***git config --get user.email --local/system/global***

**git config --get user.email** (To view config applied to current directory, be it global or local)


Setting your configurations:
**git config --global user.name “Mannu Malhotra”
git config --local user.email “mannu1200@gmail.com”
git config --system core.editor vim**  (you will need sudo permission for setting system configs)

For whole list of config variables - https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration
