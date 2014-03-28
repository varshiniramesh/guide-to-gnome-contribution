Title: Before you approach your mentor: for documentation
Slug: before-you-approach-your-mentor-documentation
Date: 2013-07-11
Category: Articles

Do you want to be mentored for writing GNOME Documentation? 

__Consider the following__:

 * The goal of being mentored is to improve the accuracy and style of writing documentation. 
 * You would gain expertise at writing documentation more quickly, if you equip yourself with these tools and skills before approaching your mentor for help.
 * Your mentor like you is a volunteer for GNOME who contributes his/her free time to help you. It would benefit your time and mentor's time to primarily concentrate on improving documentation than setting-up/debugging the tools to be used. That is to say, the tools used for documentation are easy to pick up on your own and you should do so too :-)

If yes, then these are the small essential pre-requisites you will need to possess so your mentor can help you better. However, if you get stuck, you can always ask on the IRC channel [#docs](http://chat.mibbit.com/?channel=docs&server=irc.gimp.net) on the IRC network: irc.gimp.net for one-on-one help.

## Table of Contents ##

1. When and Why do we write documentation?
1. What do I need on my computer to write documentation?
1. How to write documentation? A simple documentation bug fixed step by step.
1. How do I learn Mallard? A simple mallard page explaining how you can learn to use tags.
1. What next?

## When and Why do we write documentation?

We write documentation to address these issues:

1. No user help for help for a particular software or part of the software exists at all. 
1. To improve existing documentation. When any inconsistency is noticed in the existing user help, we report it and then write the correct user help.

## What do I need on my computer to write documentation?

1. A Gnu/Linux distribution.
1. GNOME 3.8 Desktop.
1. Familiarity with the GNOME softwares: Terminal, Gedit and Yelp.
1. Familiarity with basic Git commands.
1. An Internet connection.
1. A [documentation bug from bugzilla.gnome.org](https://bugzilla.gnome.org/buglist.cgi?type0-0-4=substring&keywords=documentation&keywords_type=allwords&field0-0-0=product&type0-0-1=substring&field0-0-1=component&field0-0-4=longdesc&resolution=FIXED&resolution=WONTFIX&resolution=DUPLICATE&resolution=NOTABUG&resolution=NOTGNOME&resolution=INCOMPLETE&resolution=INVALID&type0-0-3=substring&query_format=advanced&field0-0-3=status_whiteboard&bug_status=UNCONFIRMED&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&bug_status=NEEDINFO&bug_status=RESOLVED&bug_status=VERIFIED&field0-0-2=short_desc&type0-0-0=substring&type0-0-2=substring).

If you do not have a Gnu/Linux distribution with GNOME, please seek help to get one installed on your computer. You can go through [Guide to GNOME contribution](http://sindhus.bitbucket.org/guide-to-gnome-contribution.html) and accquaint yourself with the Terminal, installing Git, running Yelp and installing JHbuild to download and test GNOME software from git.gnome.org. 

## How to write documentation? A simple documentation bug fixed step by step.

__Pick a bug__:

[Bug 698739 - No documentation on how to add a directory path to the PATH variable](https://bugzilla.gnome.org/show_bug.cgi?id=698739)

_How did I find this bug?_ 

1. I was interested in Terminal application and visited the [https://bugzilla.gnome.org/browse.cgi?product=gnome-terminal](https://bugzilla.gnome.org/browse.cgi?product=gnome-terminal).
1. I clicked on the number next to the word "Docs" which led to the page: [https://bugzilla.gnome.org/buglist.cgi?product=gnome-terminal&bug_status=UNCONFIRMED&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&component=docs](https://bugzilla.gnome.org/buglist.cgi?product=gnome-terminal&bug_status=UNCONFIRMED&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&component=docs)
1. I saw that bug 698739 could be possible to resolve, as from the description I understood that I had to write documentation on how to add directory path to PATH variable.

__Note__: When selecting bugs, it's really a matter of reading description, the bug page and understanding _what can be done_ to resolve this. This ability comes from using the application and a Gnu/Linux distribution regularly. Try selecting and reading bugs that look familiar to you. As you read bug reports, you will be able to understand terminology, issues, descriptions about that particular software better over time.

__Get the source code__: 

1. Open [git.gnome.org](http://git.gnome.org) and search for 'terminal'.
1. Found link to gnome-terminal at 'http://git.gnome.org/browse/gnome-terminal'
1. Copy the link at the bottom of the page: 'git://git.gnome.org/gnome-terminal'.
1. Execute: `git clone git://git.gnome.org/gnome-terminal`
1. In Terminal, run: `cd gnome-terminal` to view downloaded source code.
1. `cd help/C/`
1. `ls`

We can find user help pages usually within the `help/C` directory. They have the extension ".page". Now, you will be able to see the available user help pages.

__Understand the bug__:

The reporter says...

_There is no user help instructions on how to add a location to the PATH variable_.

The developer replies:

_Help instsuctions for adding a location to the PATH variable comes within the purview of using the shell (such as bash, zsh and so on) and hence it's under the purview of the user manual for Terminal, however a link to the bash (default shell in most Gnu/Linux distribution) manual page would be helpful to the readers of the manual_.

__Decide the resolution__:

From this I understood two things:

1. Add link to the bash manual page in the user help pages.
1. Remove the page "prob-add-to-path.page.stub". By looking at the directory `../gnome-terminal/help/C` I was able to determine that such a page existed and is no longer needed.

## Iteration Number 1

__Make the change__:

1. I added the link to the "tip" that mentions about the PATH variable. I learnt the link syntax by asking on #docs channel.
1. I then used `git rm prob-add-path.page` to remove the page from git. Deletion is also a change that needs to be intimated to git, hence I used `git rm`.

__Save the change__:

1. `git add -u`
1. `git commit`

```plain

help: Add link to bash man page; bug 698739

Deleted prob-add-to-path.page.stub as discussed on bug page
is not required as instructions on how to add a location to
PATH is outside the scope of Terminal user help.
```

__Make the patch__:

1. `git format-patch HEAD~1`

__Upload the patch__:

<a href="/static/images/upload_patch.png"><img src="/static/images/upload_patch.png" style="width:500px"></a>

## Iteration Number 2

Reviewer says...

```html
Review of attachment 253553 [details]:
::: help/C/gs-execute-commands.page
@@ +60,1 @@
    </note>

I don't think we should be telling users about installing stuff to
custom locations. It's too much on the hacky side of things to do,
so I would prefer to see the note removed as it is not relevant to
the content of the page.
```

This means that the note we had written is giving out the wrong meaning. We want to be helpful in our user manual. Hence a link to the bash manual page would be helpful. Let's revise it like to mean something on the lines of that if the command the user executed was not found then it's possible that the
terminal does not know where the program is. If you want to, you can tell the terminal where the program is, for which you have to consult the BASH manual page.

So my new "note" tag would be:

```html
<p>Programs could be installed to different locations on your computer. If you
have tried to execute a program and received a terminal output, <em>No command
found</em>, then you would want to consult the <link href="info:bash"><app>BASH
</app></link> manual page for help on adding locations to the <code>PATH</code>
variable.</p>
```

Now my steps would be same from the first iteration:

1. Save the change
1. Make the patch
1. Upload the patch

After which we wait for the reviewer to review the revised patch. You will receive an e-mail notification when another review has been posted. The reviewer may mark your patch as "NEEDS-WORK" which means you will need to revise the patch to bring a suitable resolution to the bug. 

These iterations could last until the reviewer sees that the resolution provided for the bug report is the correct one. Once the reviewer accepts a patch, he/she will mark the patch as "accepted-commit_now" and then the patch will be accepted (technical term: commited) to the main source code (that is, git.gnome.org/gnome-terminal).

## How do I learn Mallard? A simple mallard page explaining how you can learn to use tags. ##

```
<page xmlns="http://projectmallard.org/1.0/"
      xmlns:e="http://projectmallard.org/experimental/"
      type="topic" style="task"
      id="about-me">

  <info>
    <desc>A Mallard page about Sindhu S.</desc>
    <revision version="0.1" date="2013-05-29" status="draft"/>
    <credit type="author">
      <name>Sindhu S</name>
      <email>sindhus@gnome.org</email>
    </credit>
  </info>

 <title>About me!</title>

<!--Example of syntax to add an image -->
    <figure>
    <media type="image" src="sindhu_kittykat.jpg">
      <p>This is me along with my documentation mentor, kittykat.</p>
    </media>
  </figure>

<!--Example of syntax to add a paragraph -->

  <p>Hello, I am Sindhu from Mangalore, a small coastal town in South India.
  I have a Bachelor's degree in Computer Applications. I have previously
  worked at Ministry of Home Affairs, Govt. of India. I am currently awaiting
  a master’s degree in Computer Science from The Oxford College of Science,
  Bangalore. I am an Outreach Program for Women alumni having written user
  manuals for GNOME projects: Terminal and Dictionary. I am a member of the
  GNOME Foundation.</p>

<!--Example of syntax to add an section -->
  <section id="started-using-linux">
    <title>How I started using Gnu/Linux</title>

    <p>I was given a free Ubuntu CD in 2006, and since been using GNU/Linux
    and GNOME. During the course of these years, I taught myself tools
    like:</p>

<!--Example of syntax to add an unordered (that is, bulleted) list of items-->
    <list style="unordered">
      <item>
        <p>Git</p>
      </item>
      <item>
        <p>Compiling from source</p>
      </item>
      <item>
        <p>Mallard and some XML</p>
      </item>
    </list>

  </section>

  <section id="started-contributing">
    <title>How I started contributing to GNOME</title>

    <p>In 2012, a friend helped me make a small contribution and that paved
    way for me to channel my passion for FLOSS to benefit the community
    directly.</p>
  </section>

  <section id="contribution-list">
    <title>My contribution so far...</title>

<!--Example of syntax to add a table with border and shading-->

    <table frame="all" rules="rows cols" shade="all">
      <tr>
        <td><p>Project</p></td> <td><p>Number of commits</p></td>
      </tr>
      <tr>
        <td><p>Tomboy</p></td> <td><p>3</p></td>
      </tr>
      <tr>
        <td><p>Dictionary</p></td> <td><p>19</p></td>
      </tr>
      <tr>
        <td><p>Terminal</p></td> <td><p>143</p></td>
      </tr>
      <tr>
        <td><p>Gnote</p></td> <td><p>2</p></td>
      </tr>
      <tr>
        <td><p>libgit2-glib</p></td> <td><p>2</p></td>
      </tr>
      <tr>
        <td><p>Gitg</p></td> <td><p>26</p></td>
      </tr>
      <tr>
        <td><p>Empathy</p></td> <td><p>3</p></td>
      </tr>
      <tr>
        <td><p>GTK+</p></td> <td><p>1</p></td>
      </tr>
      <tr>
        <td><p>Gedit</p></td> <td><p>20</p></td>
      </tr>
      <tr>
        <td><p>Rhythmbox</p></td> <td><p>1</p></td>
      </tr>
      <tr>
        <td><p>Evince</p></td> <td><p></p></td>
      </tr>
      <tr>
        <td><p>Banshee</p></td> <td><p>6</p></td>
      </tr>
      <tr>
        <td><p>JHbuild</p></td> <td><p>2</p></td>
      </tr>
    </table>

    <p>I am interested in coding, bug triaging and documentation. My everyday
    effort is to spread the word about how easy it is to make your first
    contribution and build incrementally from there.</p>

<!--Example of syntax to add a note with the style type - tip -->

    <note style="tip">
      <p>I have also written
        <link href="http://sindhus.bitbucket.org/guide-to-gnome-contribution.html">Guide to GNOME Contribution</link>.</p>
    </note>
  </section>

  <section id="currently">
    <title>What am I doing currently?</title>

    <p>These are my top priorities:</p>

<!--Example of syntax to add a steps type list -->

    <steps>
      <item>
        <p>I am this summer's GSOC intern for
    <link href="https://wiki.gnome.org/Gitg">Gitg</link> - the Git UI client. I aim to release Gitg with
    format-patch and interactive rebase support. </p>
      </item>
      <item>
        <p>I am also the new maintainer
    of Dictionary. I am planning on fixing a few bugs in the old code and planning up a simple vala version of Dictionary from scratch.</p>
      </item>
    </steps>

<!--Example of syntax to add a note -->

    <note>
      <p>I have spoken about FLOSS and making contributions at my school. I
      also help out students and faculty in using Gnu/Linux, GNOME and
      preparing for FLOSS internships at my school.</p>
    </note>
  </section>

  <section id="other-interests">
    <title>Other interests</title>

<!--Example of syntax to add a link to an external resouce -->

    <p>In my spare time, I like practising minimalism with my lifestyle,
    reading on my kindle, writing socially relevant notes based on personal
    experiences, and finding clever ways to <link href="http://sindhus.bitbucket.org/category/recipes.html">cook</link> and pack tasty meals.</p>
  </section>

  <p>Powered by <media type="image" src="mallard-badge.png"/></p>

</page>

```

__Result__

<a href="/static/images/before-you-approach-your-mentor-page.png"><img src="/static/images/before-you-approach-your-mentor-page.png" style="width:500px"></a>

__To see the full mallard page__: 

1. `git clone git@bitbucket.org:sindhus/about-me.git`
1. `cd about-me`
1. `yelp about-me.page`

__Go ahead, edit the page!__

Now that you have a example page to work, edit it. Replace information about me with yours! Write about anything that interests, your family, your friends, a recent trip, your city, plants, animals, anything that you would love to write about! Play with the tags, rearrange the sections as you please. If you want to learn more tags, use [projectmallard.org](http://projectmallard.org/about/learn/index) as reference.

## Explanation of Mallard tags

Here are a few things to remember about tags and pages:

 * Tags are used to build a user help page.
 * A tag opened must be closed.
 * Tags can be nested; when nesting tags, innermost tag must be closed first and then so on.
 * You can check if all the tags you have used in your *.page are correct with help of `yelp-check validate <name-of-page>.page`
 * To view how user help pages look like use `yelp <name-of-page>.page`

__The basic tags of Mallard are__:

 _<page>_

This tag is used to create the structure of the user help page. This tag has a property (called technically as ''style'') that allows you make a page of either type: ''guide'' or ''task''. 

Guide pages are those that contain links to other help pages. 
Example: index.page

Task pages are those that contain instructions and user help.
Example: alerts.page (which we will write here).

```html
<info></info>

This tag is used to specify information pertaining to the page.
Other tags such as <revision>, <author> and <desc> are placed
within this tag.
```
```html
<revision></revision>

This tag is used to specify the version of the software for which
user help is being written. 
```

```html
<author></author>

This tag is used to specify the author who has created and written
or edited the page.
```

```html
<desc></desc>

This tag is used to give a short description to the page.
```

```html
<title></title>

This tag is used to give a title within tags like
<page>, <section>, <steps> and <list>.
```

```html
<p></p>

This tag is used to write texts in paragraph.
```

```html
<list>
  <item><p></p></item>
</list>

This tag is used when you want to insert a list
(by default, an unordered list) where contents are not in any
order nor have precedence over each other. That means, they are
more or less equal in importance or their importance doesn't matter.
```

```html
<steps>
  <item><p></p></item>
</steps>

This tag is used when you have to describe steps a user needs to
undertake in order to achieve a task. Example: Open a File,
Import a Playlist, Delete and so on.
```

```html
<section></section>

This tag is used to create sections. Sections are used when a page
contains multiple categories of related information but have
separate set of text associated with them.
```

## What's next?

This document was written to walk you through the essentials required to start resolving simple documentation bugs. As you progress, you will learn more Mallard tags and git commands. Your mentor will be able to help you out with advanced topics as solve more and more bugs.

If you would like to make this guide better for other newcomers, please feel free to clone it from [Guide to GNOME contribution](https://github.com/sindhus/guide-to-gnome-contribution) github repository. Github also allows for ["Pull Requests"](https://help.github.com/articles/using-pull-requests), which means you can create a copy of this guide in your github account, make changes and submit it to me for acceptance into my repository!

Good luck and go forth!