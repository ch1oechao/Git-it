###Git it

####Configure Git

when you install the git you could know the gir version
by this following command:

	$ git --version
	
then you will get the git version

Set your name: 

	$ git config --global user.name "your name"

Set your email:

	$ git config --global user.email "youremail@example.com"

####Repositories

You will tell Git what your project is and Git will start tracking all of the changes to that folder. Files added or subtracted or even a single letter in a single file changed -- all of it's tracked and time stamped by Git.
That's version control.

Using Terminal to do all of things about Git!

#####Create a Repository

To make a new folder:

	$ mkdir your-folder-name

To go into that folder:

	$ cd your-folder-name

To create a new Git instance for a project:

	$ git init

That's it! It will just return you to a new line.

**Tips:**

List the items in a folder

	$ ls

Turn Git on for a folder

	$ git init

#####Create a New File

Now that you've got a repository started, add a file to it.

See if there are changes listed:

	$ git status

Then add the file you just created to the files you'd like to commit to change

	$ git add README.md

Finally, commit thoes changes to the repository's history with a short description of the updates.

	$ git commit -m "you commit message"

#####Make More Changes

Now add another line to README.md and save.

In the terminal, you can view the difference between the file now and how it was at your last commit.

	$ git diff

**Tips:**

Check status of changes to a repository
	
	$ git status

View changes to files

	$ git diff

Add a file's change to be commited

	$ git add FILENAME

To add all files changes 

	$ git add .

To commit the changes you've added with a short message describing the changes

	$ git commit -m "your commit message"


####Better, together

The repository you've created so far i just on your computer, which is handy, but makes it pettry hard to share and work with others on.

So, just create a GitHub account and start a fun trip!

#####Create a GitHub Account

Add your GitHub username to your configuration:

	$ git config --global user.username YOUNAME

####Remotes

When you put something on GitHub, that copy lives on one of GitHub's servers. This makes it a remote repository because it is not on your computer, but on a server, "remote" and somewhere else.

By pushing your local (on your computer) changes to it, you keep it up to date.

Others can always get the latest from your project by pulling your changes down from the remote (and onto their computer). This is how everyone can work on a project together without needing access to your computer where your local copy is stored.


#####Create a Remote Repository

You want to sync your local version with one stored on GitHub.com called the remote version. So first create an empty remote repository on GitHub.com

#####Readme.md, .gitignores and Licenses

There are common files in open source projects.

A ```README.md``` explains what the project is, how to use it, and ofter times, how to contribute..

A ```.gitignore``` is alist of files that Git should not track, for instance, files with passwords = =

A ```license``` file is the type of license you put on your project.

#####Connect your Local to your Remote

Now you've got an empty repository started on GitHub.com. At the top you'll see 'Quick Setup', make sure the 'HTTP' button is selected and copy the address --- this is the location of your repository on GitHub's servers.

Back in your terminal, and inside of the 'your-folder-name' folder that you initialized as a Git repository in the earlier challenge, youwant to tell Git the location of the remote version on GitHub's servers. You can have multiple remotes so each requires a name.For your main one, this is commonly named origin.

	$ git remote add origin URLFROMGITHUB

Your local repository now knows where your remote one named 'origin' lives on GitHub's servers. Think of it as adding a name and address on speed dial --- now when you need to send something there, you can.

#####Push Work to your Remote

Next you want to push everything you've done locally to GitHub. Ideally you want to stay in sync, meaning your local and remote versions match.

Git has a branching system so that you can work on different parts of project at different times. We'll learn more about that later, but by default th first branch is named 'master'. When you push form a projct, you tell Git the branch name you want and the name of remote that it lives on.

In this case, we'll send our branch named 'master' to our remote on GitHub named 'origin'.

	$ git push origin master

Now go to GitHub and refresh the page of your repository. Now, everything is the same locally and remotely.

**Tips:**

Add remote connections

	$ git remote add REMOTENAME URL

Set a URL to a remote

	$ git remote set-url REMOTENAME URL

Pull in changes

	$ git pull REMOTENAME BRANCHNAME

View remote connections

	$ git remote -v

Push changes

	$ git push REMOTENAME BRANCH

####Forks And Clones

#####Forks

Now you've made a project locally and pushed it to GitHub, but that's only half the fun. The other half is working with other people and projects.

When you fork a repository, you've creating a copy of it on your GitHub account. Your fork begins its life as a remote repository. Forks are used for creating your own version of a project or contributing back fixs or features to the original project.

Once a project is forked, you then clone it from GitHub to your computer to work on locally.

#####Clone Fork Locally

Now, in terminal, clone the repository onto your computer. It will create a new folder for the repository so no need to create one. But make sure you aren't cloning it inside of another Git repository folder! 

Choose a folder to clone the repo that you want.

	$ git clone URLFROMGITHUB

Go into the folder for the fork it created

	$ cd patchwork

#####Connect to the Original Repository

But what if the original repository you forked from changes? You'll to be able to pull in those changes too. So let's add another remote connection, this time to the original, URLFROMGITHUB, repository with ites URL, found on the right hand side of the original on GitHub.

You can name this remote connection anything you want, but ofter people use 'upstream', let's use that for this.

	$ git remote add upstream URLFROMGITHUB


####Branches

Git repositories use branches to isolate work when needed. It's common practice when working on a project or with others on a project to create a branch to keep your changes in until they are ready. This way you can do your work while the main, commonly named 'master', branch stays stable. When your branch is ready, you merge it back into 'master'.

####GitHub Pages

GitHub will automatically serve and host static website files in branches named 'gh-pages'. Since the project you forked creates a website, its main branch is 'gh-pages' instead of 'master'. All sites lick this can be found using this pattern for the URL: 

	http://githubusername.github.io/repositoryname

####Create a branch

When you create a branch, Git copies everything from the current branch you're on and places it in the branch you've requested.

Type git status to see what branch you've currently on.

Create a branch and name it 'add -username', where 'username' id your username. 

	$ git branch BRANCHNAME

Now you have a branch with a new name identical to 'gh-pages'

To go into that branch and work on it, similar to use cd to change directory in terminal, you checkout a branch. Go onto your new branch:

	$ git checkout BRANCHNAME

#### Check-in

	$ git status

	$ git add FILENAME

	$ git commit -m "commit message"

Now, push origin BRANCHNAME

	$ git push origin BRANCHNAME

**Tips:**

You can create and switch to a branch in one line:

	$ git checkout -b BRANCHNAME

Create a new branch:

	$ git branch BRANCHNAME

Move onto a branch:

	$ git checkout BRANCHNAME

List the branches:

	$ git branch

Rename a branch you're currently on:

	$ git branch -m NEWBRANCHNAME

Verify what branch you're working on

	$ git status

####Pull Never Out Of Date

#####Pulling from a Remote

If you're working on something with someone you need to stay up to date with the latest state. So you'll want to pull in any changes that may have been made.

$ git pull REMOTENAME BRANCHNAME

If nothing's changed, it will tell you 'Already up-to-date'. If there are changes, it will merge thoes changes into your local version.

**Tips:**

Check Git status

	$ git status

Pull in changes from a remote branch

	$ git oull REMOTENAME REMOTEBRANCH

See changes to the remote before you pull in

	$ git fetch --dry-run

####Pull Requests

When you make changes and impovements to a project you've forked, often you'll want to send thoes changes to the maintainer of the original and requeat that they pull the changes into the original so that everyone can benefit from the updates --- that's a pull request


####Merge Locally

Your pull request has benn merged! Now, since you know that you definitely want those updates in your forked version, and your branch is in good working order, merge it into the main branch on your forked repository, in this case, 'gh-pages'.

First, move into the branch you want to merge into --- in this case, branch 'gh-pages'.

	$ git checkout gh-pages

Now tell Git what branch you want to merge in --- in this case, your feature branch that begins with 'add-'.

	$ git merge BRANCHNAME

Tidy up by deleting your feature branch how that it has benn merged.

	$ git branch -d BRANCHNAME

You can also delete the branch form your fork on GitHub:

	$ git push REMOTENAME --delete BRANCHNAME

####Pull from Upstream

And last but not least, if you pull in updates from the original, you'll be up to date and have a version too.

To pull from the original upstream:

	$ git pull upstream gh-pages

**Tips:**

Merge a branch into current branch
	
	$ git merge BRANCHNAME

Changes the branch you're working on

	$ git checkout BRANCHNAME

Delete a local branch

	$ git branch -d BRANCHNAME

Pull from a remote branch

	$ git pull REMOTENAME BRANCHNAME
























































































































































































































































