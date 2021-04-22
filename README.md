# GitCheatSheet and Command Line

This is the summary of the Git and the command line usage where you can see brefly summary of these topics.


# The command Line

The Command Line is where you can manipulate files using your keyboard, that means that there won't be any graphical interface on your PC, and also means that you must memorize the majority of the commands.

## Some comands of you can use

### To create or delete directories

To create directories, you can use the command ```mkdir <foldernamehere>``` where "foldernamehere" is where you can put the name you wish for your folder

To remove directories, you can use the command ```rmdir <foldernamehere>``` where "foldernamehere" is the name of the folder you want to delete, but you can use it only when there are no files inside the directory.
To remove the directory with any other files inside, use the command ```rm -rf <foldernamehere>```

### Navigate in the command line

To navigate to a folder, we use the command ```cd <directoryhere>``` where "directoryhere" is the directory you want to navigate.
If you want to navigate to several folders, use the command ```cd <directory1>/<directory2>/<directory3>/``` where directory1, 2 and 3 are the directories where you want to navigate.
To go back to a directory or several directories, use ```cd ..``` or ```cd ../../../```

Pro note: To quickly complete a directory name, use the tab key.

### Compare in command line

To compare files in the command line, we use the command ```diff <file1> <file2>``` where "file1" and "file2" are the files you wish to compare.
For example, to compare text files, use the command ```diff file1.txt file2.txt```

### Find files, folder and inside files

To find files, folder and inside files, use the command ```find . -name <first letters of file to find>\*```
The command above is case sensitive, but if you want to use the isensitive version of this command, use -iname instead of -name.

### Create and edit text files

To create a file and edit, use command ```nano <filename.fileext>``` where "filename" is file you want to use, and "fileext" is the extension you want to use.
This will open a file editor called nano, from there, you can start editing the file, when you finish editing, hold the ctrl key and then the x key.
Then the program will ask you if you want to save the file, use y key for yes or the n key for no.
If you say yes, the program will prompt you a file name, once you have the file name ready, push the enter or return key.

### Get state of the computer

To get state of the computer, use the command ```lshw```, this will display all the information, but if you want short, add the --short command at the end of "lshw".

# Git

Git is the version control for programs, and also for the sake of controlling the versions and so on.

Below Git we can find centres for the version control, such as GitHub (which is the page where your are reading this Markdown), GitLab, etc.

In this centres you can find other Gits, called repositories, in those repositories is where you can control the versions of programs you are coding.

Now let's talk about some commands for this summary:


# Installing Git

There are many ways to install Git, and it depends from operating system that you are using.
```sudo apt-get/apt install git```
This command will install Git and it's components for the correct usage of git on Linux on Debian.
```sudo yum install git```
Git for Fedora.
```git```
For MAC, the first time, you will be prompted to install it.

# Configuring Git

```git config --global user.name <yourgitcentreusername>```specifies the location where you will going to upload your submissions. "yourgitcentreusername" is the username where you are going to upload you commits.
```git config --global user.email <yourgitcentreemail>```
"yourgitcentreemail" is the e-mail where you are registered in your preferred git centre.

Also, you can set you default editor for Git in case Git prompts you to add a message for a certain option.
```git config --global core.editor <yourpreferrededitor>```
This is the command to set the editor where <yourpreferrededitor> is where you input your editor for git.

# Getting a repository

There are two ways for getting a repository:

## Initializing a repository

```git init```
This will create a new subdirectory called .git, which contains the necessary files for the repository.

git add <yourfile.extension>
git add LICENSE
git add README.md
// You need to add this to your file before commiting, so we use this command

git commit // Start to commit, but you need to leave a message
git commit -m "<yourcommitmessage>" // Skips the leaving the message option

## Cloning a repository

git clone // Clones the repository
git clone <url> // Clones from a url, where url is the link of the repository you want to clone
git clone <url> yourdirectory // Clones from a url, in a specific directory

# Saving changes to a repository

## Getting the status of the repository

git status // Shows the status of the files if they are new files or modified files status
git status -s
git status --short
// Short mode of git status

## Ignoring files

```.gitignore``` is the file for the files to be ignored.

Rules:
- The blank lines or lines that starts with # are ignored.
- Put the *.ext on a line, where the ext means to an extension that you wish that Git ignore.
- Put the .[ext1ext2]where the both ext1 and the ext2 are the extensions that you wish Git to ignore
- Put the *~, where the files with ~ should be ignored.
- Put / at the end a pattern to specify a directory.
- Put / at the start of the pattern to avoid recursivity or infinite or reverse 
- Put ! to negate a pattern

Example of .gitignore

```
# Files with .out will be ignored
*.out

# Files on this directory will be ignored
test/

# Files with .a will be ignored
*.a

#But the file test.out will be tracked, even if .out files are ignored
!test.out
```

## Staged and unstaged changes

git diff // Command to view the changes of the actual repository.
git diff <yourfile> // Command to view changes of specific file.
// yourfile is the file you wish to see their differences.

// To go across the file, press the Enter key to go more beyond the file
// If you want to quit at anytime, you press the Q key.


git diff --staged
git diff --cached
// Options to view what files will be added in next commit.


## Commiting changes

git commit //Doing this, Git will open your editor to enter a message for your commit

Example
```
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# On branch master
# Your branch is up-to-date with 'origin/master'.
#
# Changes to be committed:
#	modified:   README.md
#	new file:   c.c
#
```
git commit -m // Option to type a message, also you need to put the message in quotes.

## Skipping the Staging Area

git commit -a // You will not only add the files, it will also add all the already tracked files.

## Removing a file

git rm <yourfile> // Removes a file from Git, yourfile is the file that you are going to delete
git rm --cached <yourfile> //Deletes the file from Git, but no for the repository.
// yourfile is the file you wish Git to stop tracking.


## Moving files

git mv <infile> <outfile> //It is used for renaming and moving.
// infile and outfile are the names you wish to rename.

# Viewing the history

git log // Shows all the commits you made.

git log -p // Shows the commits And the changes you have made in your Git.
// Putting a number -n will show you just an specific entry or entries. 
// It's similar to ```git diff``` but with more information.
git log --stat // Shows you the changes that you have made, insertions and deletions.
git log --pretty //This will change the format that the commits will be shown
git log --pretty=oneline // Shows the commits in one single line

git log --pretty=format //You specify the format you want to use, you can follow this table for format:
%H // Commit Hash
%h // Commit Hash (Abbreviated)
%T // Tree Hash
%t // Tree Hash (Abbreviated)
%P // Parent Hashes
%p // Parent Hashes (Abbreviated)
%an // Author Name
%ae // Author E-mail
%ad // Author Date
%ar // Author Date, relative
%cn // Committer Name 
%ce // Committer Email
%cd // Commiter Date
%cr // Commiter Date, relative
%s // Subject

//Author and Committer are similar
//Although Author is the person who made the work
// The Committer is the person who last applied the work.

git log --graph // Getts an ASCII graph to view your commits and branches.

//You can find many other options on other sources.


