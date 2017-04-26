# Git Basic Commands

## Init a repository

To initialize to a repository we have to use the command
*`git init`.

This commmand will create hidden `.git` folder into the sub-folder of the project folder.

Every commit will have a comment / description (this is for every change).
With `git log` you can show all commints, refers to a timeline that match with the branch concept. For the moment we are going to work in a __master__ branch. The name the repository have is master (this is the principal banch).

This command is used to include the file into the status of __pre commit__.
*`git add` 

We must do it in two steps in order to put the message that can explain why you are commit the file. Also is usefull because the commit provide a unity in the project. This is perfect for big projects, for instance the team can work in a part of the website as 'files structure'.. This is the great reason for the __staging__.

`git commit` The commit is always following with a comment wraped by quotations.

In case you not write any message the edit bin open in the screen, whit one of this commands you force to exit from:

* `esc + :`
* `q!` 
* `wq!` 


## Track first changes

First time our files are *untracked*

To start tracking our files we have to `commit` them

To `commit` files we have to do the following...

Image we have an `index.html` file. We can start tracking it by doing...

```git init
git add index.html
git commit -m "first commit"
```

If you want to see changes, you can use the command `git diff` before the git
to see all the logs use thhis command:
*`log --stat`  

Another interesting command is:
*`git clone` 

This comand is useful to put all the info of a
*`fork` 

This is a command use for delete all files in a directory 
*`rm -rf  / rm dir`

Uh oh, looks like there have been some additions and changes to the octocat family. Let's take a look at what is different from our last commit by using the git diff command.



#Notes about git

Git is very usefill to have a repository of all changes a file you create has had along the time.

There are some commands we must know to acomplish our mission to use git right.

####1. Select the path of folder do you want work with

```
$ cd path/to/project/folder
$ git init
```

####2. Check what files there are included into this folder, includind the hidden files and folder (as `.git`)


```
$ ls -la
```

If you did a  `git init` a folder .git was created. Note that this folder is empty, no simgle copy was created by the moment. The screeen could show you something as:

```
$ ls -la
total 128
drwxr-xr-x  18 joseangel  staff   612 Apr 12 14:44 .
drwxr-xr-x   9 joseangel  staff   306 Apr 12 00:16 ..
-rw-r--r--@  1 joseangel  staff  6148 Apr 12 00:17 .DS_Store
drwxr-xr-x  12 joseangel  staff   408 Apr 12 19:15 .git
-rw-r--r--@  1 joseangel  staff  1262 Apr 12 09:14 Hexadecimal.js
-rw-r--r--@  1 joseangel  staff   441 Apr 11 23:38 calculation_ja.js
-rw-r--r--@  1 joseangel  staff   474 Apr 12 00:14 calculator_ja.js
-rw-r--r--   1 joseangel  staff   565 Apr 12 14:58 encodeWord.js
-rw-r--r--   1 joseangel  staff   312 Apr 12 09:27 getFullName.js
-rw-r--r--@  1 joseangel  staff   492 Apr 11 23:51 integer_number_range_ja.js
-rw-r--r--   1 joseangel  staff   364 Apr 12 14:43 isBoolean.js
-rw-r--r--   1 joseangel  staff   232 Apr 12 09:42 isNumber.js
-rw-r--r--   1 joseangel  staff   274 Apr 12 11:43 isString.js
```

####3. Making a commit. Now its time to create you first commit.
 
```$ git add -A
$ git commit -m "Initial commit"
```

Look at the `-m`, it means you must write a message between quotations in order to advise others (and yourself) about what kind of changes you are done in the files.

####4. Next step: clonnig the content.

####5. pushing changes

Your changes are now in the HEAD of your local working copy. To send those changes to your remote repository, execute 

`git push origin master`

Change master to whatever branch you want to push your changes to. 

If you have not cloned an existing repository and want to connect your repository to a remote server, you need to add it with
git remote add origin <server>
Now you are able to push your changes to the selected remote server

The "git log" command is used to display the project's commit history:


`$ git log`

`git log -p` 

Git also allows you to. Use the "-p" flag with the "git log" command to display the detailed changes that happened in each commit


At the image  you can see the differents situatios of your project.

* The **working copy** means the content you are working on. This is not ready 
to be cloned. Here you can have tracked and not tracked files. Tracked files could be staged or not staged. It depends of you.

* The **stating area** is the space where you put your content ready to be commited. 

* Finally you have the files into the **local repository** or .git folder ready to be upload to a remote repository.

![image] (https://www.git-tower.com/learn/content/01-git/01-ebook/en/01-command-line/02-basics/07-working-on-your-project/staging-area-file-status.png)

##Big rules about commit

1. Commit only related changes. This means, do not mix diferent aspects of your work at ht esame commit in order to have control and order.

2. Write Good Commit Messages. Its very important supply great info because you or your partners cona forget the kind of changes you were donne.

  Begin your message with a short summary of your changes (up to 50 characters as a guideline). Separate it from the following body by including a blank line. The body of your message should provide detailed answers to the following questions: What was the motivation for the change? How does it differ from the previous version?


/starbot repos php phyton css html
*