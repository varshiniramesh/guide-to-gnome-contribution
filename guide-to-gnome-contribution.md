Title: Guide to GNOME Contribution
Slug: guide-to-gnome-contribution
Date: 2013-07-11
Category: Articles

* Are you interested in contributing code to GNOME?
* Are you interested in writing Documentation for GNOME?

This page discusses the options available to set up a development environment to contribute to GNOME, that is, the tools you need to setup, the information you need to keep track of and so on.

These are the small requirements with regards to familiarity with technical terms while reading this document:

1. Do you have Ubuntu GNOME installed?
Please note this guide assumes you have [Ubuntu GNOME](http://ubuntugnome.org/) installed on your computer. This distribution is easy to set up, manage and is quite popular among computer literate masses. Installation procedure itself is not covered under this guide as it can make the guide that much longer to read. 

While all commands mentioned in this guide should work on most other Gnu/Linux distributions as well, however you _may_ encounter issues specific to that particular distribution. Predicting all of them are of course, impossible and beyong the scope of this document. However, I can point you to the general direction - to resolve issues, you might want to seek help in communication mediums (such as mailing lists, forums, Question and Answer websites) meant for that distribution. For example, you are reading this guide but using Fedora _and_ have an issue, try approaching [Fedora Forum](http://www.fedoraforum.org/). Similarly for other distributions.

1. Do you know what a terminal is? Do you know the meaning of "execute"?
1. Are you familiar with the terms 'binaries/executables', 'library/libraries'?
1. Do you know which part of a terminal is called prompt?

If yes, then go forth!
If no, then please seek help with these basic requisites. Once you have installed Ubuntu GNOME and are familiar with the terminology listed above, you can use the knowledge in this document for your benefit!

## Table Of Contents ##

1. Explore Bugzilla.
1. Your interaction with the source code.
1. Why should I set up a development environment?
1. JHbuild & Setup.
1. Preparing JHbuild to compile modules from source.
1. Configuring your JHbuild.
1. JHbuild comamnds.
1. Compile a GNOME module from source.
1. Sign up to mailing lists.
1. Documentation specific resources.
1. Learn Mallard.
1. Chat on IRC.

The question "How to contribute to GNOME"? has a simple answer. "See a bug? Saw a bug? Need a feature? Upload a patch!". You can see problems (that is, "see bugs") when you use GNOME for your daily computing needs such as looking up a definition in Dictionary, listening to music in Rhythmbox, taking notes in Tomboy, Bijiben or Gnote. [Dictionary](https://wiki.gnome.org/Dictionary), [Rhythmbox](https://wiki.gnome.org/Rhythmbox), [Tomboy](https://wiki.gnome.org/Apps/Tomboy), [Bijiben](https://wiki.gnome.org/Apps/Bijiben) and [Gnote](https://wiki.gnome.org/Gnote) are examples of some GNOME applications.

You can also search for problems that other people have reported about ("Saw a bug") by exploring a website called "Bugzilla" for GNOME and for when you need a new feature in GNOME - all of these have the same solution - File a patch!

We will get to the meaning of "File a patch" in a few paragraphs.

## Explore Bugzilla ##

Bugs are problems encountered when you use any software. Bug reports are pages where such problems are described and filed on a accessible system such as a webpage. Bugzilla is a software in the form of a website, that allows you to report, track and manage bugs. [Visit GNOME Bugzilla](http://bugzilla.gnome.org).

You will have to register yourself an account on Bugzilla with an e-mail address that would want to receive bug mail (notifications of bugs being filed, being commented on, closed and/or resolved and so on). When you login with an account, you will be able to comment on bugs filed, ask for help on specific bug pages and track other users' bugzilla activity.

__Where does one look for problems?__

[Browse GNOME Bugzilla](https://bugzilla.gnome.org/browse.cgi). The website is fairly intuitive and you should be able to navigate different software projects by selecting your interested projects from the dropdown menu and then clicking on "Show product". 

Don't know what projects you would be interested in? In your GNOME desktop, ask yourself which is your favorite application in GNOME? Is it the Dictionary? Is it Terminal? is it Rhythmbox that plays you music? Is it GNOME Desktop itself? Once you decide on a application, search for the name in the dropdown menu and explore the project's bug reports!

__Note__: Certain applications although installable in GNOME, are _not_ managed by GNOME. For example: applications that are a part of another desktop environment, such as KDE (Krita, Kate and so on), Ecllipse, Codeblocks and so on. These are independent projects that have their separate community. Their development process and procedures are independent of GNOME.

__How do I find bugs that are easy to solve?__

Every bugzilla product page has a listing of "gnome-love" bugs. gnome-love tag is used to indicate that the bug is easy to fix and some assistance will also be provided should people be available to do so. Click on "gnome-love" link on a bug page to see gnome-love marked bugs for that particular project.

_Example_:

<a href="/static/images/gnome_love_bugs_dictionary.png"><img src="/static/images/gnome_love_bugs_dictionary.png" style="width:500px"></a>

__ How do I give my solutions to these problems/bugs?__

Now that you know what problems/bugs are, you might be interested in giving solutions to them, that is to say "fixing a bug". The solutions should be provided by you in a file. This file is called a "patch". This is what we mean when we say "Upload a patch", that is give solution to a problem!

__How can I know more features and explore Bugzilla?__

If you want a short guide, I have written a blog post about the different ways you can subscribe to relevant bug mail, see [hunt for bugs as a newcomer](http://sindhus.bitbucket.org/bugzilla-tricks-for-bug-hungry-newbies.html). For in depth knowledge, Andre Klapper, has written [a series of posts explaining hidden useful features of Bugzilla](http://blogs.gnome.org/aklapper/category/computer/bugzilla/). 

## Your interaction with the source code ##

Free and Open source software  (FLOSS) is a collaborative effort from people spread throughout the world. In order to keep track of changes from these varied people, a revision control system is in place, that is to say it's important to know among ourselves that who is making what changes to the source code of a project. "Revisions" refers to changes in the source code. GNOME uses Git  to track revisions and conrol who has access to make such revisions.

Your first step in contributing to GNOME starts with you downloading the source code for a project.

__Why should I get source code?__

Problems in software arise because of the way source code of a project is written. It may be faulty, it may be inconsistent within different parts of the software itself, it may not accomodate features required by users and so on. These problems are bugs and bugs need to be resolved with solutions. So to provide solutions to a bug of a project, you have to follow this flow:

1. Get the source code of the project.
1. Locate the faulty lines of code (the lines that are causing the problem) OR where lines of code are missing.
1. Make the change (that is, write the solution) in the source code.
1. Submit your changes as a file. These changes that you just made, are your solution to the problem that you see reported on Bugzilla. This solution is called a "Patch" file.

__ Terminal: to execute commands__

Git is a command line software, which means you interact with Git using a terminal. In GNOME, to issue commands in the command line, use the application "Terminal". 

The blinking cursor in the terminal is called 'prompt'. A blinking cursor indicates that terminal is ready to execute your commands. After typing your command, you press "Enter" key. When you open Terminal for the very first time, it's default location will be set to your HOME folder. So, all the following commands listed from here on in this article will create content in your HOME folder. For now, there are only two commands you will need to know to naviagte between directories using a Terminal.

1. `cd some-directory-name` 
`cd` means 'change directory' and _some-directory-name_ can be replaced with the name of the directory you wish to navigate to.
1. `ls some-directory-name`
`ls` means you want to view the list of files in the directory your Terminal has _changed_ into. 

__Tip__: To know which directory your terminal is currently at, type `pwd`.
'pwd' is short for 'present' working directory'. You should see an output like `/home/sindhus/gnome-dictionary`.

'cd` is a linux commands. Teaching elaborately how to use linux command is beyond the scope of this document. To learn more on how to navigate back and forth between directories, please see [Using The Terminal](https://help.ubuntu.com/community/UsingTheTerminal).

__How do I install Git?__

1. Make sure you are connected to the Internet.
1. Open Terminal.
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

You can check if you have git installed on your computer by following these commands:

1. Type `mkdir test` and press Enter. This command will create a new directory called 'test'.
1. Type `cd test` and press Enter. This means, your terminal is now _inside_ the 'test' directory.
1. Type `git init` and press Enter. This command will initialize git to _watch_ 'test' directory for files added, removed and revisions made to 'test' directory. If this command fails, then you do not have git installed on your computer. If this command succeeds, you should see an output like this: `Initialized empty Git repository in /home/sindhus/test/.git/`. Instead of 
sindhus' which is my username, the address will have your username.

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

You have selected a bug to solve? Great! You know how to fix it? Great! You have made the change? Great! How do I know show these changes to the world? This procedure is called _making a patch_. A patch is a file that contains the changes you made to the source code in order to fix an issue.

To make a patch, in the git repository of the project you made changes to:

1. Add changed files. This command tells git that you are ready to save the changes to these files. This command means that you are adding _all_ files you changed, to be saved: `git add -u`. If want to add each file one by one, then use `git add /path/to/file`. Replace /path/to/file with actual path file name and it's extension, of course. You can press "Tab" key to compelete the path and file name after typing some letters of the same.

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

1. Commit (that is, save these changes) with a message: `git commit -m "Your commit message goes here"`. For example: `git commit -m "Help: Added definition for strategies"`. For this the output would look like:

```
sindhus@leh:~/checkout/gnome/gnome-dictionary/help/C$ git commit -m "Added definition for strategies"
[stubs 9d18361] Added definition for strategies
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

1. Open the bug page in your web browser.
1. At the bottom of the page, click "Add an attachement", this will take you to a page where you can _attach_ (that is, upload) your patch file to the bug page.

In the directory (that is, the git repository) where you generated the patch, you can either move this patch to another folder to keep for future use or delete it, as per your convinience. 

__Where can I learn more about Git?__

You will be able to appreciate how git was developed, learn the advanced features it provides, accquire deeper understanding of how git works by reading these popular books and resources:

 * [Git-scm book](http://git-scm.com/book)
 * [Wikipedia git page](http://en.wikipedia.org/wiki/Git_(software))

## Why should I setup a development environment?

Contributions to open source projects, be it code or documentation or design to a project, are always "Upstream". Upstream means that your work will be incorporated in the current source code and released later during the release cycle of a product. This means you have to work with the code available in the development repository of the project.

Since contributions are always upstream, we are chasing a moving target, really. To contribute, its good practise if you have the product built from source - source that is available in the development repository. Mainly, because you don't want to fix or build something that has already been accomplished or components of the product have changed, thus breaking your contribution.

Software in development repositories are prone to breakage and so if you mix stable binaries (executables that come with your Gnu/Linux distribution) with development binaries (the software that you will compile from source), you will end up with a broken system (that is, unusable) every now and then. 

To avoid these hassles, one must keep development environment separate from their regular/daily usage operating system (such as your Gnu/Linux distribution). There are three ways to achieve this:

__Method 1: Install your development environment on a separate machine__

This method is suitable if you..

* Have a spare computer with small processing power.

AND

* Do not have the time to be physically present in front of a computer, when it is compiling code from source.
 
As development libraries and products are available as executables as well, one can set up a Gnu/Linux distribution with repositories that have daily updated development builds of projects. For example, Fedora provides development builds in it's _Rawhide_ repositories.

__Method 2: Use virtualization to set-up a development environment in your daily-use computer__

* Is your preferred choice of an operating system different from the one you intend to development for? 
* Are you short on time to set up a new operating system?
* Are you afraid to dual boot? (perhaps, those having UEFI, especially on Macbooks)

If yes to any of the above, virtualization could be the answer. For example, you could use OS X along with VirtualBox and Vagrant software to quickly set up Gnu/Linux and use it for development. Vagrant has a large user base and hence you will be able to find "images" of most popular Gnu/Linux distributions for quick usage.

Usage of virtualization software have the advantage that the environment is transferrable and re-usable on other computers as well. However, such virtualized development environments are not suitable for those...

1. With computers with small processing power.
1. Who work with GUI applications, such as the GNOME desktop itself.

Using virtualized environments means that your computer is now allocating your computer's hardware resources and processing power between two operating systems. That means, your host operating system (such as OS X from previous example) could run slower when you are using the guest operating system (such as Gnu/Linux from VirtualBox).

__Method 3: Use JHbuild and keep an isolated development environment in your daily-use computer__

This method is suitable for those who would like to keep their development environment and regular use operating system on a single computer. JHbuild is essentially a couple of scripts

## JHbuild & Set-up ##

JHbuild is a software that compiles GNOME modules (libraries and programs) from source. It makes compiling applications like Gnote, Tomboy, Dictionary, Rhythmbox, Terminal among many others, much easier. Applications are referred to as "modules" within jhbuild. 

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

## Preparing JHbuild to compile modules from source ##

Now, we can move on preparing jhbuild to compile from source. 

Jhbuild keeps compiled GNOME modules in a separate location, away from the stable binaries of your Gnu/Linux distribution. Hence it is necessary to create this separate location. 

Another purpose of this section is that, some GNOME module would need compilers & build tools and specific libraries called "development libraries" for a project. Example: gcc is a popular C compiler and a requisite in building most GNOME modules. It is not installed by default in most Gnu/Linux distributions.

To understand "development libraries", consider the FLOSS alternative for .NET framework - Mono. To compile, mono we would require "libmono-dev". The prefix "lib"  indicates that it is a library and the suffix "-dev" indicates it this software package contains headers. Headers are necessary to compile software. From your C programming classes, you would know that *.h are header files required to access some functions. Libraries are collection of such functions. 

__To prepare JHbuild__:

1. `touch ~/.jhbuildrc`
1. cp ~/jhbuild/examples/sample.jhbuildrc ~/./jhbuildrc
1. `chmod 0755 /opt`
1. `mkdir /opt/gnome`
1. `jhbuild sanitycheck`
1. `jhbuild build gtk+`

The last command is builds GTK+ library. Since, GTK+ is the most basic and thoroughly used library throughout GNOME modules, building GTK+ should pull in all dependencies needed for most other GNOME modules you will build later :-) Building GTK+ could take anywhere between 2 hours to 6 hours+ depending on two main factors: 

1. Speed of your internet connection (to download GNOME modules' source code from git.gnome.org).
1. Speed of your processor (to compile the downloaded modules one by one).

## Configuring your JHbuild ##

The configuration for JHbuild exists in ~/.jhbuildrc. You can configure this according to your needs. For example, compiling Webkit library is time consuming and it is readily available as a binary in most package repositories. Hence in the .jhbuildrc file, we can add it to a section called "skip" and thus telling jhbuild to _skip_ building Webkit from source.

My .jhbuildrc looks like this:

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

#For later use
#emerillon
#gnome-sudoku
#gnome-getting-started-docs
#gnome-tweak-tool
#seahorse
#ostree
#totem

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

## JHbuild commands ##

Here is a list of a few basic and useful commands of jhbuild to be familiar with when you are using Jhbuild to build GNOME modules. You don't have to memorise them, just keep them handy for quick reference :-)

* To list all dependencies for a module: `jhbuild list <module-name>`.
* To build a module including it's dependencies: `jhbuild build <module-name>`.
* To build a module with existing source code (that is, _not_ downloading .fresh changes from git.gnome.org): `jhbuild build -n <module-name>`.
* To build a module without building it's dependencies: `jhbuild buildone <module-name>`.
* To run a sucessfully built module: `jhbuild run <module-name`.
* To see where a binary of a jhbuild module is located: `jhbuild run which <module-name`.
* To compile a GNOME module: `jhbuild make`
* To enter into JHbuild shell: `jhbuild shell`.

## Compile a GNOME from source ##

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
Do you have the modules already compiled? 

1. If yes, you may build your module with `jhbuild buildone gnome-dictionary`.
1. If no, then build your module with `jhbuild build gnome-dictionary`.

## Sign up to mailing lists ##

GNOME Mailing lists are hubs of information pertaining to any project. In addition to IRC, to keep abreast of the latest news with the projects you are interested in, it is recommended you be subscribed to the following lists from the many available here: 

[https://mail.gnome.org/mailman/listinfo](https://mail.gnome.org/mailman/listinfo)

__How can I read what discussions have happened on a mailing list before I subscribe to it?__

You may want to read discussions that are on going or have previously been on the mailing list in order to make sure you are subscribing to mailing list which is useful and relevant to your interests. You can read previous discussions in the "Archives" section. For example: [https://mail.gnome.org/archives/gnome-doc-list/](https://mail.gnome.org/archives/gnome-doc-list/). Here, the conversations are grouped based on replies to an e-mail under each calendar year and month.

__How will mailing list be useful to me?__

Mailing lists can be used to:

1. Discuss programming problems. Example:
1. Asking for reviews for patches filed (when nobody has reviewed your patch even after a long time). Example:
1. Discuss a new feature you have in mind for the project?

__Caution!__: Please don't post topics outside of a mailing lists's concern. For example: Don't post on desktop-devel-list asking for help on how to use GNOME, post it on gnome-love. gnome-love list helps newcomers on a wide range of topics. Posting on a mailing list means that _all_ people who are subscribed to a mailing list will get a copy of your e-mail and if it's not relevant to the list's topic, it will be ignored and you will not receive help you require.

__Caution__: Please remember that before you approach a mailing list, you must do your research. Mailing list is not an alternative to Google search. Mailing list must be your last resort to seeking help.

__Tip__: Use a simple password that is different from your e-mail/other important accounts' password.

## Documentation specific resources ##

If you want to know what you can do for Documenation in GNOME, check the following pages:

1. [Contributing to GNOME Documentation, how?](https://wiki.gnome.org/DocumentationProject/Contributing)
1. [What are the tasks available in Documentation?](https://wiki.gnome.org/DocumentationProject/Tasks)
1. [Who can I approach to help me with contribution to Documentation?](https://wiki.gnome.org/GnomeLove/Mentors#Design.2C_Documentation.2C_Engagement.2C_etc.).

__Docs related mailing lists__:

 * [gnome-doc-devel-list](https://mail.gnome.org/mailman/listinfo/gnome-doc-devel-list).
 * [gnome-doc-list](https://mail.gnome.org/mailman/listinfo/gnome-doc-list).

### Learn Mallard ###

You can learn Mallard in the following ways:'

 * Refer to the official website: [projectmallard.org](projectmallard.org)
 * Refer to the offline mallard specifications by: `git clone git://gitorious.org/projectmallard/projectmallard.git`. To view the specifications after cloning:

 1. `cd projectmallard`
 1. `cd 1.0`
 1. `yelp index.page`.

 * [Keep a mallard cheat sheet handy](http://gitorious.org/projectmallard/mallard-cheat-sheets). 

__Teaching yourself Mallard__:

The best way to teach yourself any new language is to build something with it. To teach yourself mallard, try writing a page using mallard about topics that interest you. For example: Yourself!, knowledge you have acquired in Open Source etc. 

Examples:

 * http://sindhus.bitbucket.org/docs/gnome-visa/index.html - A few Mallard based help pages about Visa application procedure in India. 

## Chat on IRC! ##

TOWRITE!