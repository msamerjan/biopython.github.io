---
title: GitMigration
permalink: wiki/GitMigration
layout: wiki
---

Migration from CVS to Git
=========================

We are currently testing the benefits of migration to git distributed
version control.

Currently we have a git repository hosted at github.com:

<http://github.com/biopython/biopython/>

This is the official branch, it's synchronized with the main
[CVS](CVS "wikilink") trunk every hour, so it should be up to date most
of the time.

All developers and potential contributors are encouraged to try out this
repository.

Below you can find rudimentary instructions on how to develop Biopython
with git.

Prerequisites
-------------

### Installing git

First, you need to have git installed on your computer.

Git (http://git-scm.com/) is now available for all major operating
systems, you can get it

-   Linux: Git is now packaged in all major linux distributions, you
    should find it in your package manager.
-   Mac OS X: <http://code.google.com/p/git-osx-installer/>
-   Windows: There are two options:
    [MsysGit](http://code.google.com/p/msysgit/) or running the compiled
    git under Cygwin. You can find more information in \[\[this github
    guide\][1](http://github.com/guides/using-git-and-github-for-the-windows-for-newbies)\]

### Getting a github account (Optional)

Once you have git installed on your machine, you can get the code and
start developing, However, since the code is hosted at github, you can
use more features if you sign up for github account. This is completely
optional but if you do sign up all other developers will be able to see
(and review) the changes you have made.

If you dan't already have a github account:

-   create one here <http://github.com/plans> (the free plan is
    absolutely enough)
-   Upload an ssh public key by clicking on 'account' after having
    logged in

Obtaining the source code
-------------------------

There are two ways of getting the code tree onto your machine. They're
not that different, in fact both will result in a directory on your
machine containing a full copy of the repository on your machine.
However, if you have a github account, you can make your repository a
public branch of the project. If you do so, other people will be able to
easily review your code, make their own branches from it or merge it
back to the trunk.

In fact you can change this later, using the .git/config file, but to
make it easier I'll describe the two possibilities separately.

### Forking biopython using a github account

If you are logged in to github, you can go to the Biopython repository
page

[`http://github.com/biopython/biopython/tree/master`](http://github.com/biopython/biopython/tree/master)

and click on a button named 'Fork'. Yes, it's that easy.

It will create a fork (basically a copy) of the official Biopython
repository your personal account.

Now, assuming that you have git installed on your computer, execute the
following commands locally on your machine:

`git clone git@github.com:`<your username>`/biopython.git`

Where <your username>, not surprisingly, stands for your github
username. You have just created a local copy of the biopython repository
on your machine.

You may want to also link your branch with the official distribution:

`git remote add official_dist `[`git://github.com/biopython/biopython.git`](git://github.com/biopython/biopython.git)

You can find more info here:
<http://github.com/guides/keeping-a-git-fork-in-sync-with-the-forked-repo>

### Forking without a github account

Getting a copy of the repository without github account is even easier:

` git clone `[`git://github.com/biopython/biopython.git`](git://github.com/biopython/biopython.git)

This command creates a local copy of the biopython source on your
machine. However, if you want other people to see your changes without
github, you need to take care of publishing your branch yourself.

Making changes
--------------

Now you can make changes to your branch. Since your local branch is a
full repository, you can commit your changes as often as you like. In
fact, you should commit as often as possible, because smaller commits
are much better to manage and document. Let us assume you've made
changes to the file Bio/x.py. You need to add this file to your
change-set:

`git add Bio/x.py`

and now you commit:

`git commit -m "added feature Y in Bio.x"`

Your commits in git are local, i.e. they affect only your working branch
and not the whole Biopython tree or even your fork on github. You don't
need an internet connection to commit, so you can do it very often.

Once you think your changes are fine and should be reviewed by others,
you can push your changes back to the server:

`git push origin`

Other information
-----------------

There is a lot of different nice guides to using git on the web:

-   <http://github.com/guides/git-cheat-sheet>
-   <http://zrusin.blogspot.com/2007/09/git-cheat-sheet.html>
-   <http://www.kernel.org/pub/software/scm/git/docs/v1.4.4.4/cvs-migration.html>
