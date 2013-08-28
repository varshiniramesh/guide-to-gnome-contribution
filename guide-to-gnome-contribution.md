Title: Guide to GNOME Contribution
Slug: guide-to-gnome-contribution
Date: 2013-07-11
Category: Articles

* Are you interested in contributing code to GNOME?
* Are you interested in writing Documentation for GNOME?

This page discusses the big picture - all that you need to know right from taking baby steps to walking to sprinting to running full speed ahead! These are the small requirements with regards to familiarity with technical terms while reading this document:

1. Do you have Ubuntu GNOME installed?

Please note this guide assumes you have [Ubuntu GNOME](http://ubuntugnome.org/) installed on your computer. This distribution is easy to set up, manage and is quite popular among computer literate masses. Installation procedure itself is not covered under this guide as it can make the guide that much longer to read.

While all commands mentioned in this guide should work on most other Gnu/Linux distributions as well, however you _may_ encounter issues specific to that particular distribution. Predicting all of them are of course, impossible and beyong the scope of this document. However, I can point you to the general direction - to resolve issues, you might want to seek help in communication mediums (such as mailing lists, forums, Question and Answer websites) meant for that distribution. For example, you are reading this guide but using Fedora _and_ have an issue, try approaching [Fedora Forum](http://www.fedoraforum.org/). Similarly for other distributions.

1. Do you know what a terminal is? Do you know the meaning of "execute"?
1. Are you familiar with the terms 'binaries/executables'?
1. Do you know which part of a terminal is called prompt?

If yes, then go forth!
If no, then please seek help with these basic requisites. Once you have installed Ubuntu GNOME and are familiar with the terminology listed above, you can use the knowledge in this document for your benefit!

## Table Of Contents ##

1. Technical Terms
1. How to start contributing to GNOME?
1. Explore Bugzilla.
1. Your interaction with the source code.
1. Why should I set up a development environment?
1. JHbuild & Setup.
1. Sign up to mailing lists.
1. Documentation & YOU.
1. Learn Mallard.
1. Chat on IRC.
1. Make this document better!

## Technical Terms ##

These are the terms used in this document along with it's equivalents used interchangably.

| Term                     | May also be referred to as:    |
|:-------------------------|:-------------------------------|
| Program                  | Application, Executale, Binary |
| Software                 | Project, Module, Product       |
| Graphical User Interface | User Interface (UI)            |

## How to start contributing to GNOME? ##

You will require these:

1. A bug in software.
1. Source code of the software.
1. Git to download source code on to your computer.
1. Your willingness to learn how to fix a bug :-)
1. Knowledge of basic git commands to save the changes you made in the source code.
1. Git commands to send the changes made to source code.
1. Internet connection to connect to a website called bugzilla.gnome.org and upload the changes you made.

__What are bugs?__

Bugs are problems encountered when you use any software. Problems in software arise because of the way source code of a project is written. The source code may be faulty or inconsistent within parts of the software itself (Example: When the user manual does not match with user interface of the software) or the software does not have features which would be useful and so on. These problems are bugs and bugs need to be resolved with solutions.

__Where can I see bugs?__

When you use GNOME for your daily computing needs such as looking up a definition in Dictionary, listening to music in Rhythmbox, taking notes in Tomboy, Bijiben or Gnote, you will be able see problems in these software. They can be as minor as a button being too small to major as the software closing abruptly or performing sluggishly.

[Dictionary](https://wiki.gnome.org/Dictionary), [Rhythmbox](https://wiki.gnome.org/Rhythmbox), [Tomboy](https://wiki.gnome.org/Apps/Tomboy), [Bijiben](https://wiki.gnome.org/Apps/Bijiben) and [Gnote](https://wiki.gnome.org/Gnote) are examples of some GNOME applications.

__Note__: Certain applications although installable in GNOME, are _not_ managed by GNOME. For example: applications that are a part of another desktop environment, such as KDE (Krita, Kate and so on) and also Ecllipse, Codeblocks and so on. These are independent projects that have their separate community. Their development process and procedures are independent of GNOME.

__Where will I find bugs?__

Go on, read the next section!

## Explore Bugzilla ##

If you don't find a bug yourself, don't worry, there are plenty of bugs filed by others. There are webpages where problems of a software are described and filed, these are called "Bug Reports". As number of bug reports grow, managing all the bugs being filed, resolved and else becomes a task. Hence, there is a system in place called Bugzilla. It is a software in the form of a website, that allows you to report, track and manage bugs. [Visit GNOME Bugzilla](http://bugzilla.gnome.org).

You will need to register yourself on GNOME Bugzilla. You can always browse for bugs without logging in but once you login you will be able to do the following:

1. Comment on bug reports asking for help on how to resolve them, asking for review on solutions (called "Patches") you have submitted and so on.
1. Receive notifications if specific or group of bugs have been resolved.
1. Follow other user's bugzilla activity.

__Where should I start looking for bugs?__

[Browse GNOME Bugzilla](https://bugzilla.gnome.org/browse.cgi). Each software project has it's own page on Bugzilla. You can view a project's page by selecting it's name from the dropdown menu and then clicking on "Show product".

__Tip__: Don't know what projects you would be interested in? In your GNOME desktop, ask yourself which is your favorite application in GNOME? Is it the Dictionary? Is it Terminal? is it Rhythmbox that plays you music? Is it GNOME Desktop itself? Once you decide on a application, search for the name in the dropdown menu and explore the project's bug reports!

__How do I find bugs that are easy to solve?__

Every bugzilla product page has a listing of "gnome-love" bugs. gnome-love tag is used to indicate that the bug is easy to fix and some assistance will also be provided should people be available to do so. Click on "gnome-love" link on a bug page to see gnome-love marked bugs for that particular project.

_Example_:

<a href="/static/images/gnome_love_bugs_dictionary.png"><img src="/static/images/gnome_love_bugs_dictionary.png" style="width:500px"></a>

__How can I know more features and explore Bugzilla?__

If you want a short guide, see [Bugzilla Tricks For Bug Hungry Newbies](http://sindhus.bitbucket.org/bugzilla-tricks-for-bug-hungry-newbies.html). For in depth knowledge, Andre Klapper, has written [a series of posts explaining hidden useful features of Bugzilla](http://blogs.gnome.org/aklapper/category/computer/bugzilla/).

__What do you mean by fixing a bug?__

Now that you know what problems/bugs are, to contribute to GNOME, you will need to give solutions to them, that is to say "you want to fix a bug". You should know that we cannot make changes on running programs. We have to edit the source code to make the changes and compile it to get new programs. This new program is an improved version which does not have problems unlike the old program. Read the next section on how to download source code for a project!

## Your interaction with the source code ##

The workflow in fixing a bug is as follows:

1. Download the source code of the project.
1. Locate the lines of code that are causing the problem OR where lines of code are missing.
1. Make the change (that is, write the solution).
1. Submit your changes in a file.

__Now consider the following reasons__:

1. Free and Open source software (FLOSS) is a collaborative effort from people spread throughout the world. There are many people like you who make changes to source code. When multiple change the same files, there can be confusion as to who changed what. What if those changes conflict each other? What if some changes introduces a bug? What if some change makes the software unusable? 
 
1. How do we submit changes to software in such a way that other people will be able to test it? What if person A submits his change in a text file (*.txt) and person B submits his change in another format? What if person C modifies the same files as person B and both of them submit their changes together?

In order to keep track of changes, we need a system in place. Changes are also called "Revisions". Revision control software can track changes. Git is one such revision control software. GNOME uses Git. Git allows you to submit changes made to source code in a convinient format called "Patch". Thus giving all of us a common format to test changes made by others. A patch file will tell Git what changes have been made, where and that git should apply those changes automatically!

Great, __now we know why we need Git!__ Before we proceed to learn how to use Git, we should know a few terminal commands.

__Why should I learn how to use the Terminal?__

Git is a command line software, which means you _interact_ with Git using a terminal. In GNOME, to issue commands in the command line, use the application "Terminal".

__Terminal: to execute commands__

The blinking cursor in the terminal is called 'prompt'. A blinking cursor indicates that terminal is ready to execute your commands. After typing your command, you press "Enter" key. When you open Terminal for the very first time, the default location will be set to your HOME folder. So, all the following commands listed from here on in this article will create content in your HOME folder. For now, there are only two commands you will need to know to naviagte between directories using a Terminal.

1. `cd some-directory-name`
`cd` means 'change directory' and _some-directory-name_ can be replaced with the name of the directory you wish to navigate to.
1. `ls some-directory-name`
`ls` means you want to view the list of files in the directory your Terminal has _changed_ into.

__Tip__: To know which directory your terminal is currently at, type `pwd`.
'pwd' is short for 'present' working directory'. You should see an output like `/home/sindhus/gnome-dictionary`.

Teaching how to use all linux commands is beyond the scope of this document. To learn more on how to navigate back and forth between directories, please see [Using The Terminal](https://help.ubuntu.com/community/UsingTheTerminal).

__How do I install Git?__

1. Make sure you are connected to the Internet.
1. Open a Terminal.
1. Type `sudo apt-get install git-core`.

The terminal output for the installation would look like this:

```
$ sudo apt-get install git-core
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following NEW packages will be installed:
  git-core
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 1,392 B of archives.
After this operation, 21.5 kB of additional disk space will be used.
Get:1 http://in.archive.ubuntu.com/ubuntu/ raring/main git-core all 1:1.8.1.2-1 [1,392 B]
Fetched 1,392 B in 0s (4,097 B/s)
Selecting previously unselected package git-core.
(Reading database ... 259800 files and directories currently installed.)
Unpacking git-core (from .../git-core_1%3a1.8.1.2-1_all.deb) ...
Setting up git-core (1:1.8.1.2-1) ...
```

__How do I know I have git installed on my computer?__

You can check if you have git installed on your computer by running these commands:

1. Type `mkdir test` and press Enter. This command will create a new directory called 'test'.
1. Type `cd test` and press Enter. This means, your terminal is now _inside_ the 'test' directory.
1. Type `git init` and press Enter. This command will initialize git to _watch_ 'test' directory for files added, removed and revisions made to 'test' directory. If this command fails, then you do not have git installed on your computer. If this command succeeds, you should see an output like this: `Initialized empty Git repository in /home/sindhus/test/.git/`. Instead of
sindhus' which is my username, the address will have your username.

__Git commands Vs Terminal commands__

Here is the differennce between Git commands and terminal commands:

* Terminal commands are used simply to navigate between directories on a Gnu/Linux distribution. You can use them in the terminal regardless of whether you have Git installed on your computer or not.
* Git commands are to tell git what to do with changes made to files in a particular directory. You can only use git commands within a directory that is a git repository. To know if the directory is a git repository or not, check with `ls .git`. If you see an output like this:

```
sindhus@leh:~/checkout/gnome/gnome-dictionary$ ls .git
branches        config       FETCH_HEAD  hooks  info  objects    packed-refs
COMMIT_EDITMSG  description  HEAD        index  logs  ORIG_HEAD  refs
```

You are looking at a git repository. If the command returns an output like this:

```
sindhus@leh:~$ ls .git
ls: cannot access .git: No such file or directory
```

You are _not_ in a directory that is tracked by git.

__How do I download source of a GNOME project?__

All changes to software are made to the code in development repository. The development repository  is nothing but the software code (which includes files and directories) of a project that are placed at some centralized location on the internet for people to access. For example, most GNOME projects have their source code on [http://git.gnome.org](http://git.gnome.org).

To download source code of a GNOME project, these are the steps to be followed:

1. Do you know the name of the project whose source code you want to download? If yes, follow the next steps. If no, open [http://git.gnome.org](http://git.gnome.org) in your web browser and browse for the name of the project you are interested in. Note down the name. For example: gnome-dictionary.
1. type `git clone git://git.gnome.org/gnome-dictionary`.
1. You should terminal output should look like this:

```
$ git clone git://git.gnome.org/gnome-dictionary
Cloning into 'gnome-dictionary'...
remote: Counting objects: 3650, done.
remote: Compressing objects: 100% (1695/1695), done.
remote: Total 3650 (delta 2656), reused 2622 (delta 1916)
Receiving objects: 100% (3650/3650), 4.77 MiB | 298 KiB/s, done.
Resolving deltas: 100% (2656/2656), done.
```

You can view the files of the source code by navigating into the directory 'gnome-dictionary" (hint: use `cd`) and then`ls`. You should see an output like this:

```
sindhus@leh:~/checkout/gnome/gnome-dictionary$ ls
AUTHORS       COPYING.docs  gnome-dictionary.doap  NEWS    TODO
autogen.sh    COPYING.libs  help                   po
configure.ac  data          libgdict               README
COPYING       docs          Makefile.am            src
```

__How to make changes to source code?__

Each bug has a different solution. So there is no generic answer or solution to any of them. Though, bugs _can_ be classified into different categories and when some categories of bugs have a technique that can be applied to them regardless of the specific information. What are these category of bugs?

1. Programming bugs such as off by one error, incorrect display of titles, menus, shortcuts unavailable and plenty others.
1. [Documentation bugs](https://bugzilla.gnome.org/buglist.cgi?type0-0-4=substring&keywords=documentation&keywords_type=allwords&field0-0-0=product&type0-0-1=substring&field0-0-1=component&field0-0-4=longdesc&resolution=FIXED&resolution=WONTFIX&resolution=DUPLICATE&resolution=NOTABUG&resolution=NOTGNOME&resolution=INCOMPLETE&resolution=INVALID&type0-0-3=substring&query_format=advanced&field0-0-3=status_whiteboard&bug_status=UNCONFIRMED&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&bug_status=NEEDINFO&bug_status=RESOLVED&bug_status=VERIFIED&field0-0-2=short_desc&type0-0-0=substring&type0-0-2=substring) such as inconsistent user help instructions, typos (that is, spelling mistakes), missing format for content (technical term: missing markup) and so on.
1. [Translation bugs](https://bugzilla.gnome.org/buglist.cgi?type0-0-4=substring;keywords=I18N;keywords_type=allwords;field0-0-0=product;type0-0-1=substring;field0-0-1=component;field0-0-4=longdesc;resolution=FIXED;resolution=WONTFIX;resolution=DUPLICATE;resolution=NOTABUG;resolution=NOTGNOME;resolution=INCOMPLETE;resolution=INVALID;type0-0-3=substring;query_format=advanced;field0-0-3=status_whiteboard;bug_status=UNCONFIRMED;bug_status=NEW;bug_status=ASSIGNED;bug_status=REOPENED;bug_status=NEEDINFO;bug_status=RESOLVED;bug_status=VERIFIED;field0-0-2=short_desc;type0-0-0=substring;type0-0-2=substring) such as incorrect translation, outdated translation, missing translation strings and so on.
1. [String bugs](https://bugzilla.gnome.org/buglist.cgi?type0-0-4=substring;keywords=string;keywords_type=allwords;field0-0-0=product;type0-0-1=substring;field0-0-1=component;field0-0-4=longdesc;resolution=FIXED;resolution=WONTFIX;resolution=DUPLICATE;resolution=NOTABUG;resolution=NOTGNOME;resolution=INCOMPLETE;resolution=INVALID;type0-0-3=substring;query_format=advanced;field0-0-3=status_whiteboard;bug_status=UNCONFIRMED;bug_status=NEW;bug_status=ASSIGNED;bug_status=REOPENED;bug_status=NEEDINFO;bug_status=RESOLVED;bug_status=VERIFIED;field0-0-2=short_desc;type0-0-0=substring;type0-0-2=substring) such as typos in the text you see in the Graphical User Interface of a program.

If you know which bug you would like to resolve but have no clue what changes to make, you should [look up the mentor listed for the project](https://wiki.gnome.org/GnomeLove/Mentors). Most mentors can be found logged in on GNOME's IRC network. You can contact them by sending a message to their IRC usernames called "nicks". This document has a section shows you how to connect to an IRC network and chatroom. 

__How do I submit changes made to source code?__

You have selected a bug to solve? Great! You know how to fix it? Great! You have made the change? Great! How do I know show these changes to the world? This procedure is called _making a patch_. A patch is a file that contains the changes you made to the source code in order to fix an issue.

_To make a patch, in the git repository of the project you made changes to_:

1. Add changed files. This command tells git that you are ready to save the changes to these files. This command means that you are adding _all_ files you changed, to be saved: `git add -u`. 

If want to add each file one by one, then use `git add /path/to/file`. Replace /path/to/file with actual path file name and it's extension, of course. You can press "Tab" key to compelete the path and file name after typing some letters of the same.

1. Check if files you require have been added with `git status`. You should see output like this:
```
sindhus@leh:~/checkout/gnome/gnome-dictionary/help/C$ git status
# On branch stubs
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       modified:   strategies.page.stub
#
```

1. Commit (that is, save these changes) `git commit`. You will see now an editor where you can type your commit message. The commit message is needed for explaining other developers what you have done. It should follow a standard format: a short title, followed by a longer explanation, followed by a link to the relevant bug. Between this sections you should leave an empty line. Here is an example of a good commit message:

```
Add a minimal application menu

While Dictionary is a rather small application which probably
could do well with only an application menu and no menubar, this
would require a couple of design changes, as almost all actions
currently in the menus are window-specific. So for now, leave the
menubar alone and only add a minimal application menu.

https://bugzilla.gnome.org/show_bug.cgi?id=674939
```

Save and quit the editor when you are done. The terminal should display a message like this:

```
sindhus@leh:~/checkout/gnome/gnome-dictionary/help/C$ git commit
[stubs 9d18361] Add a minimal application menu
 1 file changed, 1 insertion(+), 1 deletion(-)
```

1. Check your commit with `git log`
1. Generate a patch with `git format-patch HEAD~1`
You should see terminal output like this:
```
sindhus@leh:~/checkout/gnome/gnome-dictionary/help/C$ git format-patch HEAD~1
0001-Added-definition-for-strategies.patch
```

Congragulations! Your first patch is ready to be uploaded on to bugzilla!

In the above git command, 1 indicates that git must generate the patch file for the recent most first commit. If you typed `git form-patch HEAD~2`, you would get patch files for top most (recent) plus another commit after it. To generate patches in different ways, such as combining changes of 2 commits in one patch file, execute `man git format-patch` in Terminal to go through the manual page for `git format-patch`.

__How do I submit this patch file?__

1. Open the bug page for whom you have the above changes in your web browser.
1. At the bottom of the page, click "Add an attachement", this will take you to a page where you can _attach_ (that is, upload) your patch file to the bug page.

__Where can I learn more about Git?__

You will be able to appreciate how git was developed, learn the advanced features it provides, accquire deeper understanding of how git works by reading these popular books and resources:

 * [Git-scm book](http://git-scm.com/book)
 * [Wikipedia page for Git](http://en.wikipedia.org/wiki/Git_(software))

__What happens after I upload the patch?__

After you upload the patch on to a bug page. You will see a notification like this at the top of the page:

<a href="/static/images/bug-notification.png"><img src="/static/images/bug-notification.png" style="width:500px"></a>

These are the users who are interested in bugs and patches being uploaded to that particular project. They will receive an e-mail that you have uploaded a patch on to the bug page. Among these people, will be developers, maintaners and experienced contributors. This means, they will now be interested in reviewing your patch. The review can be from anyone experienced in the project.

The reviewerer may give you a full review or only review part of the patch indicating what issues you need to resolve first. A few common possible issues with a patch can be (but not limited to):

1. Patch does not have a good commit message.
1. Your changes are not complete.
1. You changes have incorrect indenting, syntax and so on.
1. Your changes give a solution that could introduce other problems.

You should then comment if you have understood the review and ask for clarification if you haven't understood any part of the review. Here, "not understood the review" means:

1. You don't know what to do to resolve the issue when the reviewer has pointed out some part of your patch.
1. You don't know what resources you should look at in order to make the patch better.
1. You are encountering some difficulty in correcting your changes in the source code on your computer.

__I made the changes as per review, now what?__

Great! You can now follow the steps:

1. Check status with `git status`. Have you added or modified any new files relevant to this patch? If so, add them with `git add /path/to/file`.
1. To add files that you have modified, use `git add -u`.
1. Commit them with `git commit --amend`. This command will overwrite your previous commit.

__Tips__: 

1. If you want to discard your old commit and start afresh, use `git reset --hard HEAD~1`. 
1. If you want to discard _only_ the commit but keep the changes use `git reset --soft HEAD~1`.

__Lather, rinse, repeat!__

Now, you can make your patch again and re-upload it! Wait for the review and repeat the procedure until the reviewer marks your patch with "accepted_commit-now" status. You will receive an e-mail notification about it. This indicates that the patch will be incorporated into the source code located on git.gnome.org. __Congragulations, you have now successfully made your first GNOME contribution!__

__Testing your patch__

Did the reviewer ask you if you have tested your patch? If yes, then you will need to compile the software you made changes to. Compiling software from source code brings it's own set of complications especially because the computer you are using develop/modify software is also the same as the one you want to use for your daily computing needs. What are these problems? How can I develop software without breaking my operating system? Read on :-)

## Why should I setup a development environment?

Contributions to open source projects, be it code or documentation or design to a project, are always "Upstream". Upstream means that your work will be incorporated in the current source code and released as a binary later during the next release cycle of a project. You are contributing upstream when you make changes to source code available on git.gnome.org.

_Why should I have the latest source code all the time?__

So that:

1. You will _not_ end up resolving an issue that has already been solved by someone else. 
1. You will _not_ end up changing some parts of software that has already been removed.
1. You _will_ be able test your changes and see that they don't break the software usage!

__Why a separate development environment?__

Software in development repositories are prone to breakage and so if you mix stable binaries (executables that come with your Gnu/Linux distribution) with development binaries (the software that you will compile from source), you will end up with a broken system (that is, unusable) every now and then.

To avoid these hassles, one must keep development environment separate from their regular/daily usage operating system (such as your Gnu/Linux distribution). There are three ways to achieve this:

__Method 1: Install your development environment on a separate machine__

This method is suitable if you...

* Have a spare computer with small processing power.

AND

* Do not have the time to be physically present in front of a computer, when code is being compiled from source.

As development libraries and products are available as executables as well, one can set up a Gnu/Linux distribution with repositories that have daily updated development builds of projects. For example, Fedora provides development builds in it's [Rawhide](https://fedoraproject.org/wiki/Releases/Rawhide?rd=Rawhide) repositories.

__Method 2: Use virtualization to set-up a development environment in your daily-use computer__

* Is your preferred choice of an operating system different from the one you intend to development for?
* Are you short on time to set up a new operating system?
* Are you afraid to dual boot? (perhaps, those having UEFI, especially on Macbooks)

If yes to any of the above, virtualization could be the answer. For example, you could use OS X along with [VirtualBox](https://help.ubuntu.com/community/VirtualBox) and [Vagrant](http://www.vagrantup.com/) software to quickly set up Gnu/Linux and use it for development. Vagrant has a large user base and hence you will be able to find virtual machine images called ["boxes" for most popular Gnu/Linux distributions](http://www.vagrantbox.es/) for quick usage.

Usage of virtualization software have the advantage that the environment is transferrable and re-usable on other computers as well. However, such virtualized development environments are not suitable for those...

1. With computers with small processing power.
1. Who work with GUI applications, such as the GNOME desktop itself.

Visually, you are running a completely different operating system on a existing operating system. Get the picture? Ubuntu running like a program on OS X. This means that your computer is now allocating your computer's hardware resources and processing power between two operating systems. Your host operating system (such as OS X from above example) could run slower when you are using the guest operating system (such as Ubuntu from VirtualBox).

__Method 3: Use JHbuild and keep an isolated development environment in your daily-use computer__

This method is suitable for those who would like to keep their development environment and regular use operating system on a single computer.

## JHbuild & Set-up ##

JHbuild is a software that compiles GNOME modules (a single term to include both libraries and programs) from source. It makes compiling applications like Gnote, Tomboy, Dictionary, Rhythmbox, Terminal among many others, much easier. GNOME applications are also referred to as "modules" within jhbuild.

To setup JHbuild on your computer, type and run the following commands:

1. `git clone git://git.gnome.org/jhbuild
1. `cd jhbuild`
1. `./autogen.sh`
1. `make`
1. `make install`

Now, you can check if jhbuild has successfull installed itself with `which jhbuild`, you should see an output like this:

```
sindhus@leh:~/Documents/code/jhbuild$ which jhbuild
/home/sindhus/.local/bin/jhbuild
```

__Preparing JHbuild to compile modules from source__

* Jhbuild keeps compiled GNOME modules in a separate location, away from the stable binaries of your Gnu/Linux distribution. Hence it is necessary to create this separate location. 

* Another purpose of this section is that, some GNOME module would need compilers & build tools. Example: gcc is a popular C compiler and a requisite in building most GNOME modules. It is not installed by default in most Gnu/Linux distributions.

* JHbuild also requires development libraries to compile certain software from source. To understand the term "development libraries", consider the FLOSS alternative for .NET framework - [Mono](http://mono-project.com). To compile, mono we would require "libmono-dev". The prefix "lib" indicates that it is a library and the suffix "-dev" indicates it this software package contains headers. Headers are necessary to compile software. If you have taken C programming course, you would know that *.h are header files required to access some functions. Libraries are collection of such functions.

_To prepare JHbuild_:

1. cp ~/jhbuild/examples/sample.jhbuildrc ~/./jhbuildrc
1. `chmod 0755 /opt`
1. `mkdir /opt/gnome`
1. `jhbuild sanitycheck`
1. `jhbuild build gtk+`

The last command is builds GTK+ library. Since, GTK+ is the most basic and thoroughly used library throughout GNOME modules, building GTK+ should pull in all dependencies needed for most other GNOME modules you will build later :-) Building GTK+ could take anywhere between 2 hours to 6 hours+ depending on two main factors:

1. Speed of your internet connection (to download GNOME modules' source code from git.gnome.org).
1. Speed of your processor (to compile the downloaded modules one by one).

__Configuring your JHbuild__

The configuration for JHbuild exists in ~/.jhbuildrc. You can configure this according to your needs. For example, compiling the Webkit library is time consuming and it is readily available as a binary in most package repositories. Hence in the .jhbuildrc file, we can add it to a section called "skip" and thus telling jhbuild to _skip_ building Webkit from source.

_My .jhbuildrc looks like this_:

```
# -*- mode: python -*-

#repos['git.gnome.org'] = 'ssh://sindhus@git.gnome.org/git/'

moduleset = 'gnome-world-3.10'
#modules = [ 'meta-gnome-core', 'meta-gnome-apps-tested' ]

modules = ['gnome-shell',
           'epiphany',
           'tomboy',
           'gnote',
           'mutter',
           'mono'
           'system',
           'baobab',
           'empathy',
           'gedit',
           'gtk+',
           'gitg',
           'gnome-devel-docs',
           'gnome-terminal',
           'gnome-dictionary',
           'gnome-tweak-to',
           'gnome-music'
           'gnome-user-docs',
           'nautilus',
           'rhythmbox',
           'gedit-plugins',
           'gnome-shell',
           'gnome-control-center',
           'gnome-themes-standard',
           'gnome-icon-theme',
           'gnome-icon-theme-extras',
           'gnome-icon-theme-symbolic'
]

skip = [
  'iso-codes',
  'hal',
  'mozilla',
  'evolution-data-server','evolution',
  'gnome-bluetooth',
  'NetworkManager',
  'network-manager-applet',
  'pulseaudio',
  'bluez',
  'ibus',
  'ekiga',
  'liboil',
  'gnome-js-common','seed',
  'speex',
  'python2-devel'
]

use_local_modulesets = True

# what directory should the source be checked out to?
checkoutroot = os.path.expanduser('~/checkout/gnome')

# the prefix to configure/install modules to (must have write access)
prefix = '/opt/gnome'

# arguments to pass to autogen script
autogenargs = '--disable-maintainer-mode --disable-static --disable-gtk-doc --disable-systemd'
# Disable systemd for distros that don't use systemd

os.environ['CFLAGS'] = '-fno-omit-frame-pointer -g -O0 -fno-inline'
#os.environ['PYTHON'] = '/usr/bin/python2'

# On SMP systems you may use something like this to improve compilation time:
# be aware that not all modules compile correctly with make -j2
makeargs = '-j4'

# always use master for the core libs
branches['glib'] = 'master'
branches['gtk+'] = 'master'
branches['pygobject'] = 'master'
branches['vala'] = 'master'
branches['Webkit'] = 'master'
branches['gtkspell-3'] = 'http://hg.code.sf.net/p/gtkspell/code'

module_autogenargs['gtk+'] = '--disable-wayland-backend'
module_autogenargs['glib'] = '--enable-debug=yes --enable-dtrace=yes --enable-systemtap=yes --disable-visibility'
module_autogenargs['vte-3'] = '--enable-introspection'
module_autogenargs['Webkit'] = '--enable-instrospection --enable-webkit2'
module_extra_env['gobject-introspection'] = { 'PYTHON': '/usr/bin/python' }
module_extra_env['pygobject'] = {'PYTHON': 'python3'}
```

You can read [how I arrived at this configuration file here](http://sindhus.bitbucket.org/til-JHbuild-commands.html).

__JHbuild commands__

Here is a list of a few basic and useful commands of jhbuild to be familiar with when you are using Jhbuild to build GNOME modules. You don't have to memorise them, just keep them handy for quick reference :-)

* To list all dependencies for a module: `jhbuild list <module-name>`.
* To build a module including it's dependencies: `jhbuild build <module-name>`.
* To build a module with existing source code (that is, _not_ downloading .fresh changes from git.gnome.org): `jhbuild build -n <module-name>`.
* To build a module without building it's dependencies: `jhbuild buildone <module-name>`.
* To enter into JHbuild shell: `jhbuild shell`.
* To compile a GNOME module: `jhbuild make`
* To run a sucessfully built module: `jhbuild run <module-name`.
* To see where a binary of a jhbuild module is located: `jhbuild run which <module-name`.

__Compile a GNOME module from source__

The following sequence of commands show how you can compile a GNOME module:

1. Check for dependency list with `jhbuild list <module-name>`.
The list will show you order of parent > child the dependent libraries that need to be compiled before it can compile your requested GNOME module. So your requested GNOME module is always towards the end. For example: I would like to build Dictionary. The terminal output for the above command would look like:

```
sindhus@leh:~$  jhbuild list gnome-dictionary
itstool
yelp-xsl
yelp-tools
gtk-doc
glib
fontconfig
gobject-introspection
gnome-common
atk
harfbuzz
pango
gdk-pixbuf
at-spi2-core
at-spi2-atk
libxkbcommon
wayland
gtk+
gnome-dictionary
```

Do you have the depedent modules (from the start to the last but one module) already compiled?

1. If yes, you may build your module with `jhbuild buildone gnome-dictionary`.
1. If no, then build your module with `jhbuild build gnome-dictionary`.

__How to compile a GNOME module after making changes to the source code?__

The configuration _checkoutroot_ in your ~/.jhbuildrc will set the location where jhbuild will download source code for a module. The same thing as a `git clone <module-name>`.

```
# what directory should the source be checked out to?
checkoutroot = os.path.expanduser('~/checkout/gnome')
```
If you have git cloned the same project else where and made your changes there, how should jhbuild know that it should compile the git repository where you made changes and not the git repository where it simply downloaded the source code in order to build the module?

_Consider this scenario_:

1. `jhbuild build gnome-dictionary`
JHbuild will go fetch source code for dependencies and compile gnome-dictionary. The source code it downloads will be put into `~/checkout/gnome`.
1. Sometime later, I will `git clone git://git.gnome.org/gnome-dictionary` in my HOME directory. I make some changes to the code.
1. I run `jhbuild buildone gnome-dictionary`.

JHbuild will pick up gnome-dictionary source from `~/checkout/gnome/gnome-dictionary` and not changes in ~/gnome-dictionary.

To avoid this confusion, the simplest approach is to make changes in the git repository available at `~/checkout/gnome`. Otherwise, do remember that you have two places on your computer where you have a copy of the same git repository. One with changes you made locally and one without!

_To tell JHbuild to build in any git repository_:

1. `jhbuild shell`
1. `jhbuild make`

## Sign up to mailing lists ##

GNOME Mailing lists are hubs of information pertaining to any project. In addition to IRC, to keep abreast of the latest news with the projects you are interested in, it is recommended you be subscribed to the following lists from the many available here:

[https://mail.gnome.org/mailman/listinfo](https://mail.gnome.org/mailman/listinfo)

__How can I read what discussions have happened on a mailing list before I subscribe to it?__

You may want to read discussions that are on going or have previously been on the mailing list in order to make sure you are subscribing to mailing list which is useful and relevant to your interests. You can read previous discussions in the "Archives" section. For example: [https://mail.gnome.org/archives/gnome-doc-list/](https://mail.gnome.org/archives/gnome-doc-list/). Here, the conversations are grouped based on replies to an e-mail under each calendar year and month.

__How will mailing list be useful to me?__

Mailing lists can be used to:

1. Seek advice and discuss on the best practises you can adopt when it comes to using code/syntax and generally towards contributions.
1. Asking for reviews for patches filed (when nobody has reviewed your patch even after a long time). [See example](https://mail.gnome.org/archives/gnome-doc-list/2013-August/msg00016.html).
1. Discuss a new feature you have in mind for the project?

Remember that before you approach a mailing list, you must do your research. Mailing lists are not an alternative to Google search.

__Caution!__: Please don't post topics outside of a mailing lists's concern. For example: Don't post on desktop-devel-list asking for help on how to use GNOME, post it on gnome-love. gnome-love list helps newcomers on a wide range of topics. Posting on a mailing list means that _all_ people who are subscribed to a mailing list will get a copy of your e-mail and if it's not relevant to the list's topic, it will be ignored and you will not receive help you require.

__Tip__: Use a simple password that is different from your e-mail/other important accounts' password.

## Documentation & YOU ##

The part where you make changes in source code is the part that differs for categories of contribution. To contribute to GNOME documentation, the specific knowledge you will require are:

1. How to use the software you are writing help instructions for?

You can become familiar with the software only by using it thoroughly. Use it in your daily computing needs means that you are also testing it for bugs!

1. Familiarity with "Yelp".

Yelp is the software that displays User Help files. To see Desktop Help, press F1 on your GNOME Desktop.

1. Mallard syntax.

Mallard is the language used to write GNOME Documentation. This language will tell Yelp how to present certain information. By present we mean, how the styles and formatting will be appear when you view a user help page.

__How should I learn Mallard?__

You can learn Mallard in the following ways:'

 * Refer to the official website: [projectmallard.org](projectmallard.org)
 * Refer to the offline mallard specifications by: `git clone git://gitorious.org/projectmallard/projectmallard.git`. To view the specifications after cloning:

 1. `cd projectmallard`
 1. `cd 1.0`
 1. `yelp index.page`.

 * [Keep a mallard cheat sheet handy](http://gitorious.org/projectmallard/mallard-cheat-sheets).

__Teaching yourself Mallard__:

The best way to teach yourself any new language is to build something with it. To teach yourself mallard, try writing a page using mallard about topics that interest you. For example: Yourself!, knowledge you have acquired in Open Source etc. Thus when you are writing prose, you will look up tags to use, thus automatically referring to projectmallard.org. Writing something of interest you will allow you to learn without having to memorise.

For example [Visa Help](http://sindhus.bitbucket.org/docs/gnome-visa/index.html) - A few Mallard based help pages about Visa application procedure in India.

__Documentation Resouces__

1. [Contributing to GNOME Documentation, how?](https://wiki.gnome.org/DocumentationProject/Contributing)
1. [What are the tasks available in Documentation?](https://wiki.gnome.org/DocumentationProject/Tasks)
1. [Who can I approach to help me with contribution to Documentation?](https://wiki.gnome.org/GnomeLove/Mentors#Design.2C_Documentation.2C_Engagement.2C_etc.).

_Docs related mailing lists_:

 * [gnome-doc-devel-list](https://mail.gnome.org/mailman/listinfo/gnome-doc-devel-list).
 * [gnome-doc-list](https://mail.gnome.org/mailman/listinfo/gnome-doc-list).

## Chat on IRC! ##

TOWRITE!

## Make this document better! ##

You can make this document better by cloning it from [Guide to GNOME contribution](https://github.com/sindhus/guide-to-gnome-contribution) github repository. Github also allows for ["Pull Requests"](https://help.github.com/articles/using-pull-requests), which means you can create a copy of this repository in your github account, make changes and submit it to me for acceptance into my repository!