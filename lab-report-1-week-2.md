# CSE 15L - Week 2 Lab Report

[Back to Home Page](index.html)

## Installing VScode
To install VScode, go to [VScode's download page](https://code.visualstudio.com/download) and download the correct version for your system. After downloading and setting up the application, you should see a screen similar to the following:

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

In the following example, `WhereAmI.java` is copied to the ieng6 account, then compiled and ran using the `javac` and `java` commands. The output of the system information when compiled and ran on the local machine versus on the server is different, which shows that the Java file was successfully copied over.

Compiling and running on local machine, and using scp to move file to server:

![Running locally and SCP command](/assets/week-2-images/image4.png)

Compiling and running on server:

![Running on server](/assets/week-2-images/image5.png)

## Setting an SSH Key
We can set up SSH keys to avoid having to re-enter our server account password each time we run `ssh` or `scp`. The command `ssh-keygen` creates a pair of public and private keys that are used by `ssh` in place of your password.

Here are the steps to set this up:
* Type `ssh-keygen` in Terminal on your local machine
* When prompted with `Enter file in which to save the key (/Users/<user-name>/.ssh/id_rsa):`, enter `/Users/<user-name>/.ssh/id_rsa`
* When prompted with `Enter passphrase`, hit enter to leave the passphrase empty
* Use `ssh` to login to the server, and use `mkdir .ssh` to create a `.ssh` directory
* Now back on your local machine, copy the created public key from the `.ssh` directory on your computer to the server using `scp /Users/<user-name>/.ssh/id_rsa.pub <your-account-name>.ucsd.edu:~/.ssh/authorized_keys`

After completing these steps, you should be able to login using `ssh` without needing to enter your password:

![SSH key login](/assets/week-2-images/image6.png)

## Optimizing Remote Running
To optimize remote running, you can combine multiple commands into one line by separating each command with a semicolon. For example, you can login using `ssh`, execute various commands, then logout using `exit` all in the same line.

Using the same `WhereAmI.java` as an example Java file for this purpose, we are able to make local edits, copy the file to the server, and compile and run the file remotely in a couple simple steps:
* Edit `WhereAmI.java` on your local machine and save the file
* Use `scp` to copy the file to the server
* Combine `ssh`, `javac`, and `java` in one line by using semicolons

Here is what this would look like in Terminal:

![Optimized remote running](/assets/week-2-images/image7.png)

[Back to Home Page](index.html)
