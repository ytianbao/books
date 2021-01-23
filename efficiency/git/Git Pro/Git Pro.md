# Pro Git

[TOC]

## License
This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License. To view a copy of this license, visit <https://creativecommons.org/licenses/by-nc-sa/3.0> or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

```question
1. License证书有什么用？
    License能表明其他人能对这份代码做什么，有什么样的权力和义务
2. 常见的License证书有哪些？
    GNU General Public License
        其他人可以复制软件、发布软件、收取费用、任意修改
    MIT License
        其他人可以使用、复制、修改软件、可以出售软件、限制是它必须附有MIT授权协议
```

## Preface by Scott Chacon
Welcome to the second edition of Pro GIt. The first edition was published over four years ago now. Since then a lot has changed and yet many important things have not. While most of the core commands and concepts are still valid today as the Git core team is pretty fantastic at keeping things backward compatible, there have been some significant additions and changes in the community surrounding Git. The second edition of this book is meant to address those changes and update the book so it can be more helpful to the new user.

```question
1. 为什么要写这本书？
    因为过了4年，虽然git的核心没有变，但是生态发生了变化，所以有必要写这本书
```

When i wrote the first edition, Git was still a relatively difficult to use and barely adopted tool for the harder core hacker. It was starting to gain steam in certain communities, but had not reached anywhere near the ubiquity it has today. Since then, nearly every open source community has adopted it. Git has made incredible progress on Windows, in the explosion of graphical user interfaces to it for all platforms, in IDE support and in business use. The Pro Git of four years ago knows about none of that. One of the main aims of this new edition is to touch on all of those new frontiers in the Git community.

```understand
    这几年Git变化了很多，变得几乎人尽皆知，可以通过此书查看近几年的变化
```

The Open Source community using Git has also exploded. When I originally sat down to write the book nearly five years ago(it took me a while to get the first version out), I had just started working at a very little known company developing a Git hosting website called GitHub. At the time of publishing there were maybe a few thousand people using the site and just four of us working on it. As I write this introduction, GitHub is announcing our 10 millionth hosted project, with nearly 5 million registered developer accounts and over 230 employees. Love it or hate it, GitHub has heavily changed large swaths of the Open Source community in a way that was barely conceivable when I sat down to write the first edition.

```understand
    作者工作在GitHub，那时候GitHub还是一个只有230人的小公司，写第一版的时候很难
```

I wrote a small section in the original version of Pro Git about GitHub as an example of hosted Git which I was never very comfortable with. I didn't much like that I was writing what I felt was essentially a community resource and also talking about my company in it. While I still don't love that conflict of interests, the importance of GitHub in the Git community is unavoidable. Instead of an example of Git hosting, I have decided to trun that part of the book into more deeply describing what GitHub is and how to effectively use it. If you are going to learn how to use Git then knowing how to use GitHub will help you take part in a huge community, which is valuable no matter which Git Host you decide to use for your own code.

The other large change in the time since the last publishing has been the development and rise of the HTTP protocol for Git network transactions. Most of the examples in the book have been changed to HTTP from SSH because it's so much simpler.

It's been amazing to watch Git grow over the past few years from a relatively obscure version control system to basically dominating commercial and open source version control. I'm happy that Pro Git has done so well and has also been able to be one of the few technical books on the market that is both quite successful and fully open source.

I hope you enjoy this updated edition of Pro Git.

## Preface by Ben Staraub
The first edtion of this book is what got me hooked on Git. This was my introduction to a style of making software that felt more natural than anything I had seen before. I had been a developer for several years by then, but this was the right trun that send me down a much more interesting path than the one I was on.

Now, years later, I'm a contributor to a major Git implementation, I've worked for the largest Git hosting company, and I've traveled the world teaching people about Git. When Scott asked if I'd be interested in working on the second edition, I didn't even have to think.

It's been a great pleasure and privilege to work on this book. I hope it helps you as much as it did me.

## Dedications
To my wife, Becky, without whom this adventure never would have begun. -- Ben

This edition is dedicated to my girls. To my wife Jessica who has supported me for all of these years and to my daughter Josephine, who will support me when I'm tool old to know what's going on. -- Scott

## Contributors
Since this is an Open Source book, we have gotten several errata and content changes donated over the years. Here are all the people who have contributed to the English version of Pro Git as an open source project. Thank you everyone for helping make this a better book for everyone.

## Introduction

You're about to spend serveral hours of your life reading about Git. Let's take a minute to explain what we have in store for you. Here is a quick summary of the ten chapters and three appendices of this book. 

In **Chapter 1**, we're going to cover Version Control Systems (VCSs) and Git basics -- no technical stuff, just what Git is, why it came about in a land full of VCSs, what sets it apart, and why so many people are using it. Then, we'll explain how to download Git and set it up for the first time if you don't already have it on your system. 

In **Chapter 2**, we will go over basic Git usage -- how to use Git in the 80% of cases you'll encounter most often. After reading this chapter, you should be able to clone a repository, see what has happened in the history of the project, modify files, and contribute changes. If the book spontaneously combusts at this point, you should already be pretty useful wielding Git in the time it takes you to go pick up another copy. 

**Chapter 3** is about the branching model in Git, often described as Git's killer feature. Here you'll learn what truly sets Git apart from the pack. When you're done, you may feel the need to spend a quiet moment pondering how you lived before Git branching was part of your life. 

**Chapter 4** will cover Git on the server. This chapter is for those of you who want to set up Git inside your organization or on your own personal server for collaboration. We will also explore various hosted options if you prefer to let someone else handle that for you. 

**Chapter 5** will go over in full detail various distributed workflows and how to accomplish them with Git. When you are done with this chapter, you should be able to work expertly with multiple remote repositories, use Git over email and deftly juggle numerous remote branches and contributed patches. 

**Chapter 6** covers the GitHub hosting service and tooling in depth. We cover signing up for and managing an account, creating and using Git repositories, common workflows to contribute to projects and to accept contributions to yours, GitHub's programmatic interface and lots of little tips to make your life easier in general. 

**Chapter 7** is about advanced Git commands. Here you will learn about topics like mastering the scary 'reset' command, using binary search to identify bugs, editing history, revision selection in detail, and a lot more. This chapter will round out your knowledge of Git so that you are truly a master. 

**Chapter 8** is about configuring your custom Git environment. This includes settng up hook scripts to enforce or encourage customized policies and using environment configuration settings so you can work the way you want to. We will also cover building your own set of scripts to enforce a custom committing policy.

**Chapter 9** deals with Git and other VCSs. This includes using Git in a Subversion(SVN) would and converting projects from other VCSs to Git. A lot of organizations wtill use SVN and are not about to change, but by this point you'll have learned the incredible power of Git -- and this chapter shows you how to cope if you still have to use a SVN server. We also cover how to import projects from several different systems in case you do convince everyone to make the plunge. 

**Chapter 10** delves into the murky yet beautiful depths of Git internals. Now that you know all abot Git and can wield it with power and grace, you can move on to discuss how Git stores its objects, what the object model is, details of packfiles, server protocols, and more. Throughout the book, we will refer to sections of this chapter in case you feel like diving deep at that point; but if you are like us and want to dive into the technical details, you may want to read Chapter 10 first. We leave that up to you.

In **Appendix A**, we look at a number of eamples of using Git in various specfic environments. We cover a number of different GUIs and IDE programming environments that you may want to use Git in and what is available for you. If you're interested in an overview of using Git in your shell, your IDE, or your text editor, take a look here. 

In **Appendix B**, we explore scripting and extending Git through tools like libgit2 and JGit. If you're interested in writing complex and fast custom tools and need low-level Git access, this is where you can see what that landscape looks like. 

Finally, in **Appendix C**, we go through all the major Git commands one at a time and review where in the book we covered them and what we did with them. If you want to know where in the book we used any specific Git command you can look that up here. 

Let's get started. 

## Getting Started
This chapter will be about getting started with Git. We will begin by explaining some background on version control tools, then move on to how to get Git running on your system and finally how to get it set up to start working with. At the end of this chapter you should understand why Git is around, why you should use it and you should be all set up to do so. 

### About Version Control
What is "version control", and thy should you care? Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later. For the examples in this book, you will use software source code as the files being version controlled, though in reality you can do this with nearly any type of file on a computer. 

If you are a graphic or web designer and want to keep every version of an image or layout (which you would most certainly want to), a Version Control System (VCS) is a very wise thing to use. It allows you to revert selected files back to a previous state, revert the entire project back to a previous state, compare changes over time, see who last modified something that might be causing a problem, who introduced an issue and when, and more. Using a VCS also generally means that if you screw things up or lose files, you can easily recover. In addition, you get all this for very little overhead.

#### Local Version Control Systems
Many people's version-control method of choice is to copy files into another directory (perhaps a time-stamped directory, if they're clever). This approach is very common because it is so simple, but it is also incredibly error prone. It is easy to forget which directory you're in and accidentally write to the wrong file or copy over files you don't mean to. 

To deal with this issue, programmers long ago developed local VCSs that had a simple database kept all the changes to files under revision control.

One of the most popular VCS tools was a system called RCS, which is still distributed with may computers today. RCS works by keeping patch sets (that is, the differences between files) in a special format on disk; it can then re-create what any file looked like at any point in time by adding up all the patches.

#### Centralized Version Control Systems
The next major issue that people encounter is that they need to collaborate with developers on other systems. To deal with this problem, Centralized Version Control Systems (CVCSs) were developed. These systems (such as CVS, Subversion, and Perforce) have a single server that containes all the versioned files, and a number of clients that check out files from that central place. For many years, this has been the standard for version control.

This setup offers many advantages, especially over local VCSs. For example, everyone knows to a certain degree what everyone else on the project is doing. Administrators have fine-grained control over who can do what, and it's far easier to administer a CVCS that it is to deal with local databases on every client. 

However, this setup also has some serious downsides. The most obvious is the single point of failure that the centralized server represents. If that server goes down for an hour, then during that hour nobody can collaborate at all or save versioned changes to anything they're working on. If the hard dist the central database is on becomes corrupted, and proper backups haven't been kept, you lose absolutely everything -- the entire history of the project except whatever single snapshots people happen to have on their local machines. Local VCS systems suffer from this same problem -- whenever you have the entire history of the peoject in a single place, you rist losing everything.

#### Distributed Version Control Systems
This is where Distributed Version Control Systems (DVCSs) step in. In a DVCS (such as Git, Mercurial, Bazaar or Darcs), clients don't just check out the lastest snapshot of the files; rather, they fully mirror the repository, including its full history. Thus, if any server dies, and these systems were collaborating via that server, any of the client repositories can be copied back up to the server to restore it. Every clone is really a full backup of all the data.

Furthermore, may of these systems deal pretty well with having serveral remote repositories they can work with, so you can collaborate with different groups of people in different ways simultaneously within the same project. This allows you to set up serveral types of workslows that aren't possible in centralized systems, such as hierarchical models. 

### A short History of Git
As with many great things in life, Git began with a bit of creative destruction and fiery controversy.

The Linux kernel is an open source software project of fairly large scope. For most of the lifetime of the Linux Kernel maintennance (1991-2002), changes to the software were passed around as patches and archived files. In 2002, the Linux kernel project bagan using a proprietary DVCS called BitKeeper. 

In 2005, the relationship between the community that developed the Linux kernel and the commercial company that developed BitKeeper broke down, and the tool's free-of-charge status was revoked. This prompted the Linux development community (and in particular Lunux Torvalds, the creator of Linux) to develop their own tool based on some of the lessons they learned while using BitKeeper. Some of the goals of the new system were as follows:

- Speed
- Simple design
- Strong support for non-linear development (thousands of parallel branches)
- Fully distributed
- Able to handle large projects like Linux kernel efficiently (speed and data size)

Since its birth in 2005, Git has evolved and matured to be easy to use and yet retain these initial qualities. It's amazingly fast, it's very efficient with large projects, and it has an incredible branching system for non-linear development (See Git Branching).

### What is Git?
So, what is Git in a nutshell? This is an important section to absorb, because if you understand what Git is and the fundamentals of how it works, then using Git effectively will probably be much easier for you. As you learn Git, try to clear your mind of the things you may know about other VCSs, such as CVS, Subversion or Perforce -- doing so will help you avoid subtle confusion when using the tool. Even though Git's user interface is fairly similar to these other VCSs, Git stores and thinks about information in a very different way, and understanding these differences will help you avoid becoming confused while using it. 

#### Snapshots, Not Differences
The major difference between Git and any other VCS (Subversion and friends included) is the way Git thinks about its data. Conceptually, most other systems store information as a list of file-based changes. These other systems (CVS, Subversion, Perforce, Bazaar, and so on) think of the information they store as a set of files and the changes made to each file over time (this is commonly described as *delta-based* version control).

Git doesn't think of or store its data this way. Instead, Git thinks of its data more like a series of snapshots of a miniature filesystem. With Git, every time you commit, or save the state of your project, Git basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot. To be efficient, if files have not changed, Git doesn't store the file again, just a link to the previous identical file it has already stored. Git thinks about its data more like a stream of snapshots.

This is an important distinction between Git and nearly all other VCSs. It makes Git reconsider almost every aspect of version control that most other systems copied from the previous generation. This makes Git more like a mini filesystem with some incredibly powerful tools build on top of it, rather than simply a VCS. We'll explore some of the benefits you gain by thinking of your data this way when we cover Git branching in Git Branching. 

#### Nearly Every Operation Is Local
Most operations in Git need only local files and resources to operate -- generally no information is needed from another computer on your network. If you're used to a CVCS where most operations have that network latency overhead, this aspect of Git will make you think that the gods of speed have blessed Git with unworldly powers. Because you have the entire history of the project right
there on your local disk, most operations seem almost instantaneous. 

For example, to browse the history of the project, Git doesn't need to go out to the server to get the history and display it for you -- it simply reads it directly from your local database. This means you see the project history almost instantly. If you want to see the changes introduced between the current version of a file and the file a month ago, Git can look up the file a month ago and don a local difference calculation, instead of having to either ask a remote server to do it or pull an older version of the file from the remote server to do it locally.

This also means that there is very little you can't do if you're offline or off VPN. If you get on an airplane or a train and want to do a little work, you can commit happily (to your local copy, remember?) until ou get to a network connection to upload. If you go home and can't get your VPN client working properly, you can still work. In many other systems, doing so is either impossible or painful. In Perforce, for example, you can't do much when you aren't connect to the server; in Subversion and CVS, you can edit files, but you can't commit changes to your database (because your database if offline). This may not seem like a huge deal, but you may be surprised what a big difference it can make. 

#### Git Has Integrity
Everything in Git is checksummed before it is stored and is then referred to by that checksum. This means it's impossible to change the contents of any file or directory without git knowing about it. This functionality is built into Git at the lowest levels and is integral to its philosophy. You can't lose information in transit or get file corruption without Git being able to detect it. 

The mechanism that Git uses for this checksumming is called a SHA-1 hash. This is a 40-character string composed of hexadecimal characters (0-9 and a-f) and calculated based on the contents of a file or directory structure in Git. A SHA-1 hash looks something like this:

```sha
    24b9da6552252987aa493b52f8696cd6d3b00373
```

You will see these hash values all over the place in Git because it uses them so much. In fact, Git stores everything in its database not by file name but by the hash value of its contents. 

#### Git Generally Only Adds Data
When you do actions in Git, nearly all of them only add data to the git database. It is hard to get the system to do anything that is not undoable or to make it erase data in any way. As with any VCS, you can lose or mess up changes you haven't committed yet, but after you commit a snapshot into Git, it is very difficult to lose, especially if you regularly push your database to another repository. 

This makes using Git a joy because we know we can experiment without the danger of severely screwing things up. For a more in-depth look at how Git stores its data and how you can recover data that seems lost, see Undoing Things. 

#### The Three States
Pay attention now -- here is the main thing to remember about git if you want the rest of your learning process to go smoothly. Git has three main states that your files can reside in: modified, staged, and committed:

- Modified means that you have changed the file but have not committed it to your database yet. 
- Staged means that you have marked a modified file in its current version to go into your next commit snapshot. 
- Commited means that the data is safely stored in your local database.

This leads us to the three main sections of a git project: the working tree, the staging area, and the git directory. 

The working tree is a single checkout of one version of the project. These files are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify.

The staging area is a file, generally contained in your Git directory, that stores information about what will go into your next commit. Its technical name in Git parlance is the "index", but the phrase "staging area" works just as well. 

The Git directory is where Git stores the metadata and object database for your project. This is the most important part of Git, and it is what is copied when you clone a repository from another computer.

The basic workflow goes something like this:
1. You modify files in your working tree. 
2. You selectively stage just those changes you want to be part of your nect commit, which adds only those changes to the staging area.
3. You do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory. 

If a particular version of a file is in the Git directory, it's considered committed. If it has been modified and was added to the stagnig area, it is staged. And if it was changed since it was checked out but has not been staged, it is modified. In Git Basics, you'll learn more about thest states and how you can either take advantage of them or skip the staged part entirely.

### The Command Line
There are a lot of different ways to use Git. There are the original command-line tools, and there are may graphical user interfaces of varying capabilities. For this book, we will be using git on the command line. For one, the command line is the only place you can run all Git commands --most of the GUIs implement only a partical subset of git functionality for simplicity. If you know how to run the command-line version, you can probably also figure out how to run the GUI version, while the opposite is not necessarily true. Also, while your choice of graphical client is a matter of personal taste, all users will have the command-line tools installed and available. 

So we will expect you to know how to open Terminal in macOS or Command Prompt or PowerShell in Windows. If you don't know what we're talking about here, you may need to stop and research that quickly so that you can follow the rest of the examples and descriptions in this book. 

### Installing Git
Before you start using Git, you have to make it available on your computer. Even if it's already installed, it's probably a good idea to update to the latest version. You can either install it as a package or via another installer, or download the source code and compile it yourself. 

***This book was written using Git version 2.8.0. Though most of the commands we use should work even in ancient versions of Git, some of them might not or might act slightly differently if you're using an older version. Since Git is quite excellent at preserving backwards compatibility, any version after 2.8 should work just fine. ***

#### Installing on Linux
If you want to install the basic Git tools on Linux via a binary intaller, you can generally do so through the package management tool that comes with your distribution. If you're on Fedora (or any closely-related RPM-based distribution, such as RHEL or CentOS), you can use dnf:

```sh
$ sudo dnf install git-all
```

If you're on a Debian-based distribution, such as Ubuntu, try apt:

```sh
$ sudo apt install git-all
```

For more options, there are instructions for installing on several different Unix distributions on the Git website, at <https://git-scm.com/download/linux>

#### Installing on macOS
There are several ways to install Git on a Mac. The easiest is probably to install the Xcode Command Line Tools. On Mavericks (10.9) or above you can do this simply by trying to run git from the Terminal the very first time. 

```sh
$ git --version
```

If you don't have it installed already, it will prompt you to install it. 

If you want a more up to date version, you can also install it via a binary installer. A macOS Git installer is maintained and available for download at the Git website, at <https://git-scm.com/download/mac>.

You can also install it as part of the GitHub for macOS install. Their GUI Git tool has an option to install command line tools as well. You can download that tool from the GitHub for macOS website, at <https://desktop.github.com>. 

#### Installing on Windows
There are also a few ways to install Git on Windows. The most official build is available for download on the Git website. Just go to <https://git-scm.com/download/win> and the download will start automatically. Note that this is a project called Git for Windows, which is separate from Git itself; for more information on it, go to <https://gitforwindows.org>.

To get an automated installation you can use the Git chocolatey package. Note that the Chocolatey package is community maintained. 

Another easy way to get Git installed is by installing GitHub Desktop. The installer includes a command line version of Git as well as the GUI. It also works well with PowerShell, and sets up solid credential caching and sane CRLF settings. We'll learn more about those things a little later, but suffice it to say they're things you want. You can download this from the GitHub Desktop website. 

#### Installing from Source

Some people may instead find it useful to install Git from source, because you'll get the most recent version. The binary installers tend to be a bit behind, thought as Git has matured in recent years, this has made less of a difference. 

If you do want to install Git from source, you need to have the following libraries that Git depends on: autotools, curl, zlib, openssl, expat, and libiconv. For example, if you're on a system that has dnf(such as Fedora) or apt-get(such as a Debian-based system), you can use one of these commands to install the minimal dependencies for compiling and installing the Git binaries:

```sh
$ sudo dnf install dh-autoreconf curl-devel expat-devel gettext-devel \
    openssl-devel per-devel zlib-devel
$ sudo apt-get install dh-autoreconf libcurl4-gnutls-dev libexpat1-dev \
    gettext libz-dev libssl-dev
```

***Users of RHEL and RHEL-derivatives like CentOS and Scientific Linux will have to enable the EPEL repository to download the docbook2X package.***

If you're using a Debian-based distribution (Debian/Ubuntu/Ubuntu-derivatives), you also need the install-info package:

```sh
$ sudo apt-get install install-info
```

If you're using a RPM-based distribution (Fedora/RHEL/RHEL-derivatives), you also need the getopt package (which is already installed on a Debian-based distro):

```sh
$ sudo dnf install getopt
```

Additionally, if you're using Fedora/RHEL/RHEL-derivatives, you need to do this:

```sh
$ sudo ln -s /usr/bin/db2x_docbook2texi /usr/bin/docbook2x-text
```

due to binary name differences. 

When you have all the necessary dependencies, you can go ahead and grab the latest tagged release tarball from several places. You can get it via the kernel.org site, at <https://www.kernel.org/pub/software/scm/git>, or the mirror on the GitHub website, at https://github.com/git/git/releases. It's generally a little clearer what the latest version is on the GitHub page, but the kernel.org page also has release signatures if you want to verify your download. 

Then, compile and install:

```sh
$ tar -zxf .git-2.8.0.tar.gz
$ cd git-2.8.0
$ make configure
$ ./configure --prefix=/usr
$ make all doc info
$ sudo make install install-doc install-html install-info
```

After this is done, you can also get Git via Git itself for updates: 

```sh
$ git clone git://git.kernel.org/pub/scm/git/git.git
```

### First-Time Git Setup

Now that you have Git on your system, you'll want to do a few things to customize your Git environment. You should have to do thest things only once on any given computer; they'll stick around between upgrades. You can also change them at any time by running through the commands again. 

Git comes with a tool called git config that lets you get and set configuration variables that control all aspects of how Git looks and operates. These variables can be stored in three different places: 

1. [path]/ect/gitconfig file: Contains values applied to every user on the system and all their repositories. If you pass the option --system to git config, it reads and writes from this file specifically. Because this is a system configuration file, you would need administrative or superuser privilege to make changes to it. 
2. ~/.gitconfig or ~/.config/git/config file: Values specific personally to you, the user. You can make Git read and write to this file specifically by passing the --global option, and this affects all of the repositories you work with on your system. 
3. config file in the Git directory (that is, .git/config) of whatever repository you're currently using: Specific to that single repository. You can force Git to read from and write this file this the --local option, but that is in fact the default. Unsurprisingly, you need to be located somewhere in a Git repository for this option to work properly. 

Each level overides values in the previous level, so values in .git/config trump those in [path]/etc/gitconfig.

On Windows systems, Git looks for the .girconfig file in the $HOME directory (C:\Users\$User) for most people. It also still looks for [path]/etc/girconfig, although it's relative to the MSys root, which is wherever you decide to install Git on your Windows system when you run the installer. If you are using version 2.x or later of Git for Windows, there is also a system-level config file at C:\Documents and Settings\All Users\Application Data\Git\config on Windows XP, and in C:\ProgramData\Git\config on Windows Vista and newer. This config file can only be changed by git config -f <file> as an admin

You can view all of your settings and where they are coming from using:

```sh
$ git config --list --show origin
```

#### Your Identity
The first thing you should do when you install Git is to set your user name and email address. This is important because every Git commit uses this information, and it's immutably baked into the commits you start creating:

```sh
$ git config --global user.name "Yao Tianbao"
$ git config --global user.email 1546607932@qq.com
```

Again, you need to do this only once if you pass the --global option, because then Git will always use that information for anything you do on that system. If you want to overide this with a different name or email address for specific projects, you can run the command without --global option when you're in that project. 

Many of the GUI tools will help you do this when you first run them. 

#### Your Editor
Now that your identity is set up, you can configure the default text editor that will be used when Git needs you to type in a message. If not configured, Git uses your system's default editor. 

If you want to use a different text editor, such as Emacs, you can do the following: 

```sh
$ git config --global core.editor emacs
```

On a Windows system, if you want to use a different text editor, you must specify the full path to its executable file. This can be different depending on how your editor is packaged. 

In the case of Notepad++, a popular programming editor, you are likely to want to use the 32-bit version, since at the time of writing the 64-bit version doesn't support all pulgins. If you are on a 32-it Windows system, or you have a 64-bit editor on a 64-bit system, you'll type something like this: 

```sh
$git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe'
-multiInst -notabbar -nosession -noPlugin"
```

***Vim, Emacs and Notepad++ are popular text editors often used by developers on Unix-based systems like Linux and macOS or a Windows system. If you are using another editor, or a 32-bit version, please find specific instructions for how to set up your favorite editor with Git in git config core.editor commands.***

***You may find, if you don't setup your editor like this, you get into a really confusing state when Git attempts to launch it. An example on a Windows system may include a prematurely terminated Git operation during a Git initiated edit.***

#### Your default branch name

By default Git will create a branch called *master* when you create a new repository with git init. From Git version 2.28 onwards, you can set a different name for the initial branch. 

To set main as the default branch name do: 

```sh
$ git config --global init.defaultBranch main
```

#### Checking Your Settings
If you want to check your configration settings, you can use the git config --list command to list all the settings gGit can find at that point:

```sh
$ git config --list
user.name=Yao Tianbao
user.email=1546607932@qq.com
color.status=auto
...
```

You may see keys more than once, because Git reads the same key from different files ([path]/etc/gitconfig and ~/.gitconfig, for example). In this case, Git uses the last value for each unique key it sees. 

You can also check what Git thinks a spacific key's value is by typing git config <key>:

```sh
$ git config user.name
```

***Since Git might read the same configration variable value from more than one file, it's possible that you have an unexpected value for one of these values and you don't know why. In cases like that, you can query Git as to the origin for that value, and it will tell you which configration file had the final say in setting that value: 

```sh
$ git config --show-origin rerere.autoUpdate
```

### Getting Help
If you never need help while using Git, there are three equivalent ways to get the comprehensive manual page(manpage) help for any of the Git commands:

```sh
$ git help <verb>$
git <verb> --help$
man git-<verb>
```

For example, you can get the manpage help for the git config command by running this:

```sh
$ git help config
```

These commands are nice because you can access them anywhere, even offline. If the manpages and this book aren't enough and you need in-person help, you can try the #git or #github channel on the Freenode IRC server, which can be found at <https://freenode.net>. These channels are regularly filled with hundreds of people who are all very knowledgeable about Git and are often willing to help. 

In addition, if you don't need the full-blown manage help, but just need a quick refresher on the available options for a Git command, you can ask for the more concise help output with the -h option, as in: 

```sh
$ git add -h
```

### Summary
You should have a basic understanding of what Git is and how it's different from any centralized version control systems you may have been using previously. You should also now have a working version of Git on your system that's set up with your personal identity. It's now timeto learn some Git basics. 

## Git Basics √

If you can read only one chapter to get going with Git, this is it. This chapter covers every basic command you need to do the vast majority of the things you'll eventally spend your time doing with Git. By the end of the chapter, you can do these yourself:
1. Be able to confirgure and initialize a repository
2. begin and stop tracking files
3. stage and commit chages
4. how to set up Git to ignore certain files and file patterns
5. how to undo mistakes quickly and easily
6. how to browse the history of your project and view changes between commits
7. how to push and pull from remote repositories

### Getting a Git Repository √

You typically obtain a git repository in one of two ways:

1. You can take a local directory that is currently not under version control, and trun it into a Git repository
2. You can clone an existing Git repository from elsewhere. 

In either case, you end up with a Git repository on your local machine, ready for work. 

#### Initializing a repository in an Existing Directory √

If you have a project directory that is currently not under version control and you want to start controlling it with Git, you first need to go to that project's directory. If you've never done this, it looks a little different depending on which system you're running:

For Linux:

```sh
$ cd /home/user/my_project
```

For macOS:

```sh
$ cd /Users/user/my_project
```

For Windows:

```sh
$ cd C:/Users/user/my_project
```

and then type:

```sh
$ git init
```

This creates a new subdirectory named .git that contains all of your necessary repository files --a Git repository skeleton. At this point, nothing in your project is tracked yet. See Git Internals for more information about exactly what files are contained in the .git directory  you just created. 

If you want to start version-controlling existing files (as opposed to an empty directory), you should probably begin tracking those files and do an initial commit. You can accomplish that with a few git add commands that specify the files you want to track, followed by a git commit:

```sh
$ git add *.c
$ git add LICENSE
$ git commit -m 'Initial project version'
```

We'll go over what these commands do in just a minute. At this point, you have a Git repository with tracked files and an initial commit. 

#### Cloning an Existing Repository √

If you want to get a copy of an existing Git repository --for example, a project you'd like to contribute to --the command you need is git clone. If you're familiar with other VCS systems such as Subversion, you'll notice that the command is "clone" and not "checkout". This is an important distinction --instead of getting just a working copy, Git receives a full copy of nearly all data that the server has. Every version of every file for the history of the project is pulled down by default when you run git clone. In fact, if your server disk gets corrupted, you can often use nearly any of the clones on any client to set the server back to the state it was in when it was cloned (you may lose some server-side hooks and such, but all the versioned data would be there --see getting git on a server for more details).

```
Note: use `nearly all data` because it clones all data except server-side hooks and such.  
```

you clone a repository with git clone <url>. For example, if you want to clone the Git linkable library called libgit2, you can do like this:

```sh
$ git clone https://github.com/libgit2/libgit2
```

That creates a directory named libgit2, initializes a .git directory inside it, pulls down all the data for that repository, and checks out a working copy of the latest version. If you go into the new libgit2 directory that just created, you'll see the project files in there ready to be worked on or used. 

If you want to clone the repository into a directory named something other than libgit2, you can specify the new directory name as an additional argument:

```sh
$ git clone https://github.com/libgit2/libgit2 mylibgit
```

That command does the same thing as the previous one, but the target directory is called mylibgit. 

Git has a number of differnt transter protocols you can use. The previous example uses the https://protocol, but you may also see git:// or user@server:path/to/repo.git, which uses the SSH transfer protocol. Getting Git on a Server will introduce all of available options the server can set up to access your Git repository and the pros and cons of each. 

### Recording Changes to the Repository √

At this point, you should have a *bona fide* Git repository on your local machine, and a checkout or *working copy* of all of its files in front of you. Typically, you'll want to start making changes and committing snapshots of those changes into your repository each time the project reaches a state you want to record.

Remember that each file in your working directory can be in one of two states: tracked or untracked. Tracked files are files that were in the last snapshot; they can be unmodified, modified, or staged. In short, tracked files are files that Git knows about. 

Untracked files are everything else -- any files in your working directory that were not in your last snapshot and are not in your staging area. When you first clone a repository, all of your files will tracked and unmodified because Git just checked them out and you haven't edited anything. 

As you edit files, Git sees them as modified, because you've changed them since your last commit. As you work, you selectively stage these modified files and then commit all those staged changes, and the cycle repeats. 

#### Checking the Status of Your Files √

The main tool you use to determine which files are in which state is the git status command. if you run this command directly after a clone, you should see something like this:

```sh
$ git status
On branch master
nothing to commit, working tree clean
```

This means you have a clean working directory; in other words, none of your tracked files are modified. Git also doesn't see any untracked files, or they would be listed here. Finally, the command tells you which branch you're on and informs you that it has not diverged from the same branch on the server. For now, that branch is always master, which is the default; you won't worry about it here. Git Branching will go over branches and references in detail. 

Let's say you add a new file to your project, a simple README file. If the file didn't exist before, and you run git status, you see your untracked file like so: 

```sh
$ echo 'My Project' > README
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README

nothing added to commit but untracked files present (use "git add" to track)
```

You can see that your new README file is untracked, because it's under the "Untracked files" heading in your status outputs. Untracked basically means that Git sees a file you didn't have in the previous snapshot(commit); Git won't start including it in your commit snapshots until you explicitly tell it to do so. It does this so you don't accidentally begin including generate binary files or other files that you did not mean to include. You do want to start including README, so let's start tracking the file. 

#### Tracking New Files √

In order to begin tracking a new file, you use the command git add . To begin tracking the README file, you can run this: 

```sh
$ git add README
```

If you run your status command again, you can see that your README file is now tracked and staged to be committed:

```sh
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   README
```

You can tell that it's staged because it's under the "Changes to be committed" heading. If you commit at this point, the version of the file at the time you ran git add is what will be in the subsequent historical snapshot. You may recall that when you ran git init earlier, you then ran git add <files> -- that was to begin tracking files in your directory. The git add command takes a path name for either a file or a directory; if it's a directory, the command adds all the files in that directory recursively. 

#### Staging Modified Files √

Let's change a file that was already tracked. If you change a previously tracked file called CONTRIBUTING.md and then run your git status command again, you get something that looks like this:

```sh
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   README

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README
```

The README.md file appears under a section named "Changes not staged for commit" --which means that a file that is tracked has been modified in the working directory but not yet staged. To stage it, you run the git add command. git add is a multipurpose command -- you use it to begin tracking new files, to stage files, and to do other things like marking merge-conflicted files as resolved. It may be helpful to think of it more as "add precisely this content to the next commit" rather than "add this file to the peoject". Let's run git add now to stage the CONTRIBUTING.md file, and then run git status again:

```sh
$ git add CONTRIBUTING.md
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
    (use "git reset HEAD <file ..." to unstage)

    new file: README
modified:   CONTRIBUTING.md
```

Both files are staged and will go into your next commit. At  this point, suppose you remember one little change that you want to make in CONTRIBUTING.md before you commit it. You open it again and make that change, and you're ready to commit. However, let's run git status one more time:

```sh
$ vim CONTRIBUTING.md
$git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
    (use "git reset HEAD <file>..." to unstage)

        new file: README
modified: CONTRIBUTING.md

Changes not staged for commit:
    (use "git add <file> ..." to update what will be committed)
    (use "git checkout -- <file> ..." to discard changes in working directory)
    modified: CONTRIBUTING.md
```

What the heck? Now CONTRIBUTING.md is listed as both staged and unstaged. How is that possible? It truns out that Git stages a file exactly as it is when you run the git add command. If you commit now, the version of CONTRIBUTING.md as it was when you last ran the git add command is how it will go into the commit, not the version of the file as it looks in your working directory when you run git commit. If you modify a file after you run git add, you have to run git add again to stage the latest version of the file: 

```sh
$ git add CONTRIBUTING.md
$ git status
Onbranch master 
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
    (use "git.reset HEAD <file>..." to unstage)

    new file: README
modified: CONTRIBUTING.md
```

#### Short Status √

While the git status output is pretty comporehensive, it's also quite wordy. Git also has a short status flag so you can see your changes in a more compact way. If you run git status -s or git status --short you get a far more simplified output from the command:

```sh
$ git status -s 
 M README
MM Rakefile
A lib/git.rb
M lib/
simplegit.rb ??
LICENSE.txt
```

New files that aren't tracked have a ?? next to them, new files that have been added to the staging area have an A, modified filed have an M and so on. There are two columns to the output --the left-hand column indicates the status of the staging area and the right-hand column indicates the status of the working tree. So for example in that output, the README file is modified in the working directory but not yet staged, while the lib/simplegit.rb gile is modified and staged. The Rakefile was modified, staged and then modified again, so there are changes to it that are both staged and unstaged. 

#### Ignoring Files

Often, you'll have a class of files that you don't want Git to automatically add or even show you as being untracked. These are generally automatically generated files such as log files or files produced by your build system. In such cases, you can create a file listing patterns to match them named .gitignore. Here is an example .gitignore file:

```sh
$ cat .gitignore
*.[oa]
*~
```

The first line tells Git to ignore any files ending in ".o" or ".a" --object and archive files that may be the product of building your code. The second line tells Git to ignore all files whose names end with a tilde(~), which is used by many text editors such as Emacs to mark temporary files. You may also include a log, tmp, or pid directory; automatically generated documentation; and so on. Setting up a .gitignore file for your new repository before you get going is generally a good idea so you don't accidentally commit files that you really don't want in your Git repository. 

The rules for the patterns you can put in the .gitignore file are as follows:

- Blank lines or lines starting with # are ignored. 
- Standard glob patterns work, and will be applied recursively throughout the entire working tree. 
- You can start patterns with a forward slash (/) to avoid recursivity. 
- You can end patterns with a forward slash (/) to specify a directory. 
- You can negate a pattern by starting it with an exclamation point(!).

Glob patterns are like simplified regular expressions that shells use. An asterisk(*) matches zero or more characters; [abc] matches any character inside the brackets(in this case a, b, or c); a question mark(?) matches a single character; and brackets enclosing characters separated by a hyphen([0-9]) matches any character between them (in this case 0 through 9). You can also use two asterisks to match nested directories; a/**/z would match a/z, a/b/z, a/b/c/z, and so on. 

Here is another example .gitignore file: 

```.gitignore
# ignore all .a files
*.a

#but do track lib.a, even though you're ignoring .a files above
!lib.a

# only ignore the TODO file in the current directory, not subdir /TODO
/TODO

# ignore all files in any directory named build
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf
```

*** GitHub maintains a fairly comprehensive list of good .gitignore file examples for dozens of projects and languages at <https://github.com/github/gitignore> if you want a starting point for your project.***

***In the simple case, a repository might have a single .gitignore file in its root directory, which applies recursively to the entire repository. However, it is also possible to have additional .gitignore files in subdirectories. The rules in these nested .gitignore files apply only to the files under the directory where they are located. The Linux kernel source repository has 206 .gitignore files. It is beyond the scope of this book to get into the details of multiple .gitignore files; see man gitignore for the details.***

#### Viewing Your Staged and Unstaged Changes

If the git status command is too vague for you --you want to know exactly what you changed, not just which files were changed -- you can use the git diff command. We'll cover git diff in more detail later, but you'll probably use it most often to answer thest two questions: What have you changed but not yet staged? And what have you staged that you are about to commit? Although git status answers those questions very generally by listing the file names, git diff shows you the exact lines added and removed -- the patch, as it were. 
let's say you edit and stage the README file again and then edit the CONTRIBUTING.md file without staging it. If you run your git status command, you once again see something like this: 

```
```

To see what you've changed but not yet staged, type git diff with no other arguments:

That command compares what is in your working directory with what is in your staging area. The result tells you the changes you've made that you haven't yet staged. 

If you want to see what you've staged that will go into your next commit, you can use git diff --staged. This command compares your staged changes to your last commit: 
```
```

It's important to note that git diff by itself doesn't show all changes made since you last commit --only changes that are still unstaged. If you've staged all of your changes, git diff will give you no output. 

For another example, if you stage the CONTRIBUTING.md file and then edit it, you can use git diff to see the changes in the file that are staged and the changes that are unstaged. If our environment looks like this:

```
```

Now you can use git diff to see what is still unstaged:

```
```

and git diff --cached to see what you've staged so far (--staged and --cached are synonyms):

```
```

***Git Diff in an External Tool We will continue to use the git diff command in various ways throughout the rest of the book. There is another way to look at these diffs if you prefer a graphical or external diff viewing program instead. If you run git difftool instead of git diff, you can view any of these diffs in software like emerge, vimdiff and many more (including commercial products). Run git difftool --tool-help to see what is available on your system.***

#### Committing Your Changes

Now that your staging area is set up the way you want it, you can commit your changes. Remember that anything that is still unstaged