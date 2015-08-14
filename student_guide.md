---
layout: default
section: Students
description: A general guide to getting started with GitHub in the CS051 lab environment.
title: Getting Started Guide
starter-code: fa2015
permalink: /studentguide/
---

## Why Git and GitHub?

The goal of implementing Git and GitHub in the CS051 lab workflow is to
optimize the distribution-submission-feedback cycle for assignments while
exposing students to industry standard tools. It will (hopefully) help students
recieve more feedback on their code and make it easier for TAs and professors
to provide that feedback.

*Git is used extensievly throughout the open source and professional
development communites, so learning about these invaluable tools will add to
the set of skills you know how to work with to become a more effective
developer. However, CS051's focus is on Object-Oriented Programming (OOP) and
design--not on Git; therefore, we will not be covering advanced Git topics
nor will we require you to know them. In some cases, as you will see as you
read below, we have wrapped multi-Git steps with simpler commands.*

At any point during the semester, **please ask questions** about Git and GitHub
if you have questions or concerns. If the Git-related instructions make no
sense, please let us know so we can clarify them!

## Tools You Will Be Using

### Eclipse IDE

Eclipse is an open-source **integrated development environment** (IDE) that we
will be using in CS051 to work on the Java assignments. (It's where you'll
spend the majority of your time developing your lab assignments.) An IDE is
software that bundles together all the various tools that are needed to write
code and run that code. It includes everything from source code editors to
debugging tools to compilers to console emulators.

### Git

Git is a distributed **version control system** (VCS) that has become the
industry-standard for development in open-soure and professional communities
thanks to the popularization and adoption of the online repository hosting
service [GitHub](#github).

Git aids in the development of software and projects by allowing the developer
(or team of developers) to take snapshots of their work as they progress. This
allows you to--at any point in the project--revert changes that you or a team
member has made. At the core of Git, you have a **repository** which is where
your code lives as well as a `.git` directory that contains the data that Git
uses to track your changes. Another key feature of Git is it's idea of
**branching**. 

In a git-managed project, the goal is to have a `master` branch that contains a
functional and deployable copy of your code. As you develop features, you will
`checkout` other branches that you can develop on. When the feature is in
deployable condition, you merge it back in with the `master` branch. (We'll
be explaining more about this in another section!)

### GitHub

[GitHub](https://github.com) is an online Git repository hosting service. It's
where you will be pulling new assignments from and pushing your submissions.

In addition to supporting many features of Git, GitHub has added extra online
features like issue tracking, inline code commenting, and Pull Requests (PR)
that we will be utilizing throughout the semester.

### EGit

EGit is an implementation of Git in the Eclipse IDE; it supports the way the
IDE sets up projects and stores the files on your computer. This plug-in also
includes a graphical user interface (GUI) to complete common Git commands
without having to use the command line (although we will be using a bit of
the command line this semester).

### Terminal

A terminal is a way to interact with a computer by giving it text commands. The
commands can include everything from making a directory (`mkdir myDirectory`)
to removing a file (`rm myFile`) to running a console application like `git`.

In Eclipse, you will be using a Terminal Emulator that will allow you to
execute basic system commands like navigating into a folder
(`cd path/to/folder`) or running Git commands and aliases we created for this
course.

## Getting Setup

You should only need to complete the steps in this section once for the lab
computers and once for your personal computer. They are instructions
specifically for Mac OSX, so if you're running any other operating system,
please contact us, and we will gladly help you get setup.

***Please read all the instructions in any given section below BEFORE clicking
the links in them!***

### Signing Up for GitHub

> **NOTE:** If you already have a GitHub account, do **NOT** sign up for a new
> account.

1. Go to [GitHub's Signup page](https://github.com/join).
2. Fill in the information on the first step using your Claremont issued email
   address. (*You can always add a personal email address later if you would
   like.*) Click next once you have completed the step.
3. On Step 2, select the **$0** plan and continue to the final step.
4. Once you have complete the GitHub registration, tell us about your account
   username so we can add you to your own private repository.

### Installing Eclipse with EGit and `OBJECTDRAW`

> This guide assumes you already have the Java JDK (1.8.x) installed.

1. Go to the this page: [Eclipse IDE for Java EE Developers][eclipse].
   
   > **WARNING:** Do not click the large orange download link at the top of
   > the page--it will make these instructions useless!

2. On the right side of the page under **Download Links** select the
   appropriate operating system. (If you're on the lab computers, select Mac
   OS X.)
3. On the next page, click the orange download button that is on the **left 
   side** of the page. **(Do not use the button that is in the upper right
   corner!)**
4. Once the file downloads, open Finder in Mac and navigate to the Downloads
   directory.
5. Double click the `.tar` file that downloaded to install Eclipse.
6. Move the application to your Applications folder by dragging the
   application that installed after Step 5 in your Downloads folder.
7. Launch Eclipse by double clicking the icon.
8. In the dialog box that appears, leave the default value and check the box
   in the lower left corner to suppress the dialog box each time you launch
   Eclipse. Then click OK.
9. In the upper right corner of the new Eclipse window, click ***Workbench***.
10. On the toolbar go to ***Window > Perspective > Open Perspective > Java***.
11. Add the Terminal to the view by clicking !["terminal"]({{ site.baseurl }}/images/terminal.png)
    in the toolbar. Then click OK in the dialog box that appears.

    > The terminal that appears will appear in the same tab as the java
    > debugger that you will rely on throughout the semester, so be sure to
    > close the terminal when you are not using it or switch tabs!

12. Now, add the EGit plug-in to the workbench by clicking ***Window > Show
    View > Other... > Git > Git Repositories***.
13. Download the `OBJECTDRAW` [library][objectdraw] and move the file into
    a permanent place.
14.	In the toolbar, click ***Eclipse > Preferences > Build Path > Classpath
    Variables***
15. Click ***New...*** on the right side.
16. In *Name*, type the following (including the capitilization): `OBJECTDRAW`
17. In *Path*, browse to the file you downloaded and moved in Step 13.
18. Then click OK twice to finish!

At this point, Eclipse should look like [this]({{ site.baseurl }}/images/env_preview.png).

### Configuring Git and Cloning the Starter Code Repository into Eclipse

1. Clone the repository.
   1. Click on **File** *>* **Import** *>* **Git** *>* **Projects from Git**
   2. Click on **Clone URI** and **Next >**.
   3. In the **Source Git Repository** dialog box that appears, copy and paste
      the following into the *URI* box: 
      `https://github.com/PomonaCS051/fa2015.git`
   4. Type in your GitHub username where it says "User" and your GitHub
      password where it says "Password". Check the box next to "Store in Secure
      Store" and click **Next >**. 
   5. Ensure the `master` branch is selected. Then click **Next >**.
2. Copy the text in the *Directory* box. Paste it somewhere safe.
   Click **Next>**
3. Ensure the box next to Lab00 is checked. Then click **Finish**
   
    > If Lab00 does not automatically appear in the package explorer,
    > expand the working directory in the Git Repositories pane 
    > and right-click to select *Import...*. Then hit next to accept the
    > default options.

4. Click the `Terminal` icon
   !["terminal"]({{ site.baseurl }}/images/terminal.png) in the top menu bar.
5. Type `cd` + a space into the window that appears and copy the contents of
   you copied and saved in step 2.  It should look something like below:   
   ```
   cd /Users/cecilsagehen/git/fa2105
   ```  
   Hit return.  
   Then copy and paste the following:  
   ```
   python configure_git.py  
   ```  
   Hit return.
   You will be prompted for your password.  Enter the password for the lab computer
   and hit return.
   Enter the remaining information as it prompts you to and hit return after each prompt.
6. Right click on the "Lab00 [fa2015 master]" project in the *Project Explorer*
   panel.  Then click on **Team** *>* **Show in Repositories View**.  The *Git
   Repositories* view should open.

## Repeated Tasks Throughout the Semester

### Getting New Assignments

### Working on Assignments

#### Branching

#### Submitting a Design

#### Developing the Code

#### Committing Your Work

### Submitting Assignments

## Reviewing TA and Professor Feedback

## Questions, Comments, Concerns

## Quick Reference

### Terminal

### Git

### GitHub

### Eclipse

[eclipse]: http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/marsr
[objectdraw]: http://eventfuljava.cs.williams.edu/library/objectdrawV1.1.2.jar