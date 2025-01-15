# CSE 15L - Week 6 Lab Report

[Back to Home Page](index.html)

## Streamlining ssh Configuration

Editing .ssh/config file:
![Editing .ssh/config file](/assets/week-6-images/part1-image1.png)

Logging in using ssh with alias:
![Logging in using ssh with alias](/assets/week-6-images/part1-image2.png)

Using scp with alias:
![Using scp with alias](/assets/week-6-images/part1-image3.png)

To edit the .ssh/config file, I used the built-in nano editor to add the relevant lines. Then, I used ssh to login using the ieng6 alias in substitution of my full account name. Lastly, I used scp to copy over a dummy text file containing "Hello World!" by using the alias.

## Setup Github Access from ieng6

Location of public key on Github and user account:
![Location of public key on Github and user account](/assets/week-6-images/part2-image1.png)
![Location of public key on Github and user account](/assets/week-6-images/part2-image2.png)

Location of private key in user account:
![Location of private key in user account](/assets/week-6-images/part2-image3.png)

Git commands to commit and push changes to Github on ieng6 account:
![Git commands to commit and push changes to Github on ieng6 account](/assets/week-6-images/part2-image4.png)

[Link for resulting commit](https://github.com/justin-chiang/markdown-parser/commit/02808311e0c3d165bbc63e4cd0e2de001f65e10d)

The location of the public key on my user account is under the ~/.ssh directory, and is called id_ed25519.pub, and the location of it on Github is under the keys settings page with the key specified for my Github account, justinchiang03@gmail.com. The location of the private key on my user account is also under the ~/.ssh directory, and is called id_ed25519. To make a commit and push to Github on my ieng6 account, in addition to setting up the key in Github settings, I also had to convert my remote URLs from HTTP to SSH, which I did using the git remote set-url origin command. Then, I followed the usual steps of making changes, which include modifying a file (MarkdownParse.java), then using git add, push, and commit, which was successful. 


## Copy whole directories with scp -r

Copying whole markdown-parse directory to ieng6 account:
![Copying whole markdown-parse directory to ieng6 account](/assets/week-6-images/part3-image1.png)

Running tests on repository on ieng6 account:
![Running tests on repository on ieng6 account](/assets/week-6-images/part3-image2.png)

Combining scp and ssh in one line command:
![Combining scp and ssh in one line command](/assets/week-6-images/part3-image3.png)

To copy over the whole markdown-parse directory to my ieng6 account, I used the scp -r command and specified the location on my ieng6 account to copy all of the files in the directory. To run tests, I used the Makefile we created in Lab 6 to automate compiling and running the tests in my tester class. To combine scp and ssh to run the tests in one line, I used scp with arguments to only copy over .java files, .md files, and the lib folder, used ssh to login to ieng6, and then compiled and ran the tester Java file.

[Back to Home Page](index.html)
