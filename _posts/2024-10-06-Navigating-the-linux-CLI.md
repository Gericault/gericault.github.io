---
layout: post
title: Navigating the Linux Command Line Interface (CLI)
date: 2024-10-06 18:30:00 +0930
---
### A quick crash course to using the Linux command line interface (CLI)
I will show you how to do the following:
- Navigate the file system
- Read files
- Manage the file system
- Filter content
- Get help in Linux

### Navigating the file system

The following commands are used to navigate the Linux file system;

**cd - change directory**

{% highlight shell %}
cd reports
{% endhighlight %}

navigates from the current working directory to its subdirectory reports

{% highlight shell %}
cd \home\cale\reports
{% endhighlight %}


navigates to the reports directory; the full pathname is required when reports is not a subfirectory of the current working directory

{% highlight shell %}
cd ..
{% endhighlight %}

Navigates to the directory that is one level above the current working directory

**ls - displays the names of files and directories**

{% highlight shell %}
ls \home\cale\reports
{% endhighlight %}

Displays the names of the files and directories in the reports directory; providing an argument that specifies the path to a directory is necessary to display the contents of a directory other than the user's current working directory.

{% highlight shell %}
ls -a
{% endhighlight %}

Displays hidden files when displaying the names of files and directories inside the current working directory.

{% highlight shell %}
ls -l
{% endhighlight %}

Displays permissions to files and directories in the current working directory; also displays other additional information such as owner name, group, file size and the time of last modification.

{% highlight shell %}
ls -la
{% endhighlight %}

displays permissions to files and directories in the current working directoy; including hidden files. Also displays other additional information. This argument is a combination of both -a and -l and combines the output of both.

**pwd - prints the working directory to the screen**

{% highlight shell %}
pwd
{% endhighlight %}

Prints the current working directory to screen, such as \home\cale

**whoami - returns the username of the current user**

{% highlight shell %}
whoami
{% endhighlight %}

returns the current username, such as cale or admin.

### Reading files
The following details commands that are helpful when reading files

**cat - displays the contents of a file**

{% highlight shell %}
cat updates.txt
{% endhighlight %}

displays the content of the updates.txt file

**head - displays the first 10 lines of a file**

{% highlight shell %}
head updates.txt
{% endhighlight %}

displays the first 10 lines of the updates.txt file

{% highlight shell %}
head -n 5 updates.txt
{% endhighlight %}

displays only the first 5 lines of the file.
the -n option allows the user to specify the _number_ of lines to return.

**less - returns the content of a file one page at a time**

{% highlight shell %}
less updates.txt
{% endhighlight %}

returns the content of updates one page at a time; the less command changes the terminal window to a display which allows users to easily move forward and backward through content.

**tail - displays the last 10 lines of a file**

{% highlight shell %}
tail updates.txt
{% endhighlight %}

displays the last 10 lines of the updates.txt file

{% highlight shell %}
tail -n 5 updates.txt
{% endhighlight %}

returns the last 5 lines of updates.txt. The -n option allows the user to specify the number of lines to return.

### Manage the file system
The following are useful when managing the file system.

**cp - copies a file or directory into a new location; the file will not be removed from the previous location**

{% highlight shell %}
cp permissions.txt /home/cale/logs
{% endhighlight %}

copies the permissions.txt from the users current working directory to the logs directory.

**mkdir - make directory**

{% highlight shell %}
mkdir network
{% endhighlight %}

creates a new directory named network in the users current working directory.

{% highlight shell %}
mkdir /home/analyst/logs/network
{% endhighlight %}

creates a new directory named network in the logs directory.
The full path is required when the target directory is not a subdirectory of the current directory.

**mv - moves a file or directory to a new location; the file is also removed from the previous location.**

{% highlight shell %}
mv permissions.txt /home/cale/logs
{% endhighlight %}

moves the permissions.txt file from the users current working directory to the logs directory.

{% highlight shell %}
mv permissions.txt perm.txt
{% endhighlight %}

moves the permissions.txt file from the users current working directory to the new file name perm.txt in the users current working directory; this results in renaming the permissions.txt file as perm.txt.

**nano - opens or creates a file in the nano CLI file editor.**

{% highlight shell %}
nano permissions.txt
{% endhighlight %}

Opens an existing permissions.txt file in the nano file editor, or creates permissions.txt in the nano file editor if it doesn't already exist in the current working directory.

**rm - remove a file**

{% highlight shell %}
rm permissions.txt
{% endhighlight %}

removes the permissions.txt file from the users current working directory

{% highlight shell %}
rm home/cale/reports/permissions.txt
{% endhighlight %}

removes the permissions.txt file from the reports directory; the fill path is required is the users current working directory is not reports.

**rmdir - remove a directory**

{% highlight shell %}
rmdir network
{% endhighlight %}

removes the empty network subdirectory of the users current working directory from the file system.

{% highlight shell %}
rm /home/cale/logs/network
{% endhighlight %}

removes the empty network directory from the file system; the full path is required when network is not a subdirectory of the current directory.

**touch - creates a new file**

{% highlight shell %}
touch permissions.txt
{% endhighlight %}

creates a new file named permissions.txt in the users current working directory

{% highlight shell %}
touch /home/cale/reports/permissions.txt
{% endhighlight %}

creates a new file named permissions in the reports directory; the full path is required if the user wants to create permissions.txt in any directory other than the current working directory.
### Filter content
These commands are useful for filtering content.

**find - searches for directories and files that meet the specified criteria**

{% highlight shell %}
find \home\cale\projects
{% endhighlight %}

searches for all files starting at the projects directory

{% highlight shell %}
find \home\cale\projects -iname "*log*"
{% endhighlight %}

searches for all files in the projects directory that contain the work log in the filename.
-iname searches for a specified string and is not case-sensitive; * is a wildcard and can represent zero or more unknown characters.

{% highlight shell %}
find \home\cale\projects -mtime -3
{% endhighlight %}

Searches for all files in the projects directory that have been modified within the past 3 days.
-mtime bases its search for files or directories that were modifed within the specified number of days.

{% highlight shell %}
find \home\cale\projects -nmin -15
{% endhighlight %}

Searches for all files in the projects directory that have been modified within the past 15 minutes.
-nmin bases its search for files or directories that were modified within the specified number of minutes.

**grep - searches within a specified file and returns all lines containing a specified string.**

{% highlight shell %}
grep OS updates.txt
{% endhighlight %}

searches the updates.txt file and returns all lines containing the string OS

**\| (piping) - sends the output of one command as the input of another command for further processing.**

{% highlight shell %}
ls \home\analyst\reports | grep users
{% endhighlight %}

redirects the standard output of ls \home\cale\reports to be standard input for the grep users command, meaning the grep users identifies files and subdirectories in the \home\cale\reports directory that contain the string users within their filename.

**There is a lot that you can do with piping, It is crucial to understand the basic concept as we will be using this later.**

### Get help in Linux
The following commands are useful when getting help in Linux.

**apropos - searches the manual page descriptions for a specified string**

{% highlight shell %}
apropos password
{% endhighlight %}

returns the manual pages of commands that contain the keyword password

{% highlight shell %}
apropos -a graph editor
{% endhighlight %}

returns the manual pages of commands that contain both keywords graph and editor.
-a species to return commands that only contain all specified strings.

**man - displays a manual page for the specified command**

{% highlight shell %}
man chown
{% endhighlight %}

displays detailed information about chown and how it works.

**whatis - displays a description of a command on a single line**

{% highlight shell %}
whatis nano
{% endhighlight %}

Displays a description of nano on a single line.