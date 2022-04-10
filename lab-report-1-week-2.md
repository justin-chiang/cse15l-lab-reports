# CSE 15L - Week 2 Lab Report

## Installing VScode
To install VScode, go to https://code.visualstudio.com/download and download the correct version for your system. After downloading and setting up the application, you should see a screen similar to the following:

![VScode screen](/assets/week-2-images/image1.png)

## Remotely Connecting
To remotely connect to your CSE 15L course-specific account on ieng6, we will utilize the Secure Shell protocol (ssh). Type `ssh <your-account-name>@ieng6.ucsd.edu` into Terminal, which will then prompt you to enter your account password. If you're connecting for the first time, it may ask if you want to continue connecting; enter yes. After entering your password, you should see an output similar to the following:

![SSH output](/assets/week-2-images/image2.png)

## Trying Some Commands
Once connected to the ieng6 server, you can try some commands in Terminal. Some useful commands include:

* `ls` - lists all files in working directory
* `cd <target-dir>` - changes directory to target directory
* `mkdir <new-dir>` - makes a new directory
* `pwd` - outputs the working directory

Here is a screenshot of some example commands:

![Trying commands output](/assets/week-2-images/image3.png)

## Moving Files with scp
We can move files from our local machine to our account on the server by using the Secure Copy protocol (scp). In Terminal, type `scp <target-file-name> <your-account-name>@ieng6.ucsd.edu`, which will move the target file to your account on the ieng6 server. After entering your password, the file will be transferred.

In the following example, WhereAmI.java is copied to the ieng6 account, then compiled and ran using the `javac` and `java` commands. The output of the system information when compiled and ran on the local machine versus on the server is different, which shows that the Java file was successfully copied over.

Compiling and running on local machine, and using scp to move file to server:

![Running locally and SCP command](/assets/week-2-images/image4.png)

Compiling and running on server:
![Running on server](/assets/week-2-images/image5.png)

## Setting an SSH Key

## Optimizing Remote Running
