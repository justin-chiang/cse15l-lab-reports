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

Link for resulting commit: N/A

The location of the public key on my user account is under the ~/.ssh directory, and is called id_rsa.pub, and the location of it on Github is under the keys page in the user settings. The location of the private key on my user account is also under the ~/.ssh directory, and is called id_rsa. I followed the steps to set up SSH between my user account and Github by specifying the authentication in the config file, but I was still unable to push to Github from my ieng6 account. I will look into and fix this for the lab resubmission. 


## Copy whole directories with scp -r

Copying whole markdown-parse directory to ieng6 account:
![Copying whole markdown-parse directory to ieng6 account](/assets/week-6-images/part3-image1.png)

Running tests on repository on ieng6 account:
![Running tests on repository on ieng6 account](/assets/week-6-images/part3-image2.png)

Combining scp and ssh in one line command:
![Combining scp and ssh in one line command](/assets/week-6-images/part3-image3.png)

To copy over the whole markdown-parse directory to my ieng6 account, I used the scp -r command and specified the location on my ieng6 account to copy all of the files in the directory. To run tests, I used the Makefile we created in Lab 6 to automate compiling and running the tests in my tester class. To combine scp and ssh to run the tests in one line, I used scp with arguments to only copy over .java files, .md files, and the lib folder, used ssh to login to ieng6, and then compiled and ran the tester Java file.

[Back to Home Page](index.html)
