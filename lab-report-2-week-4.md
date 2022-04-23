# CSE 15L - Week 4 Lab Report

[Back to Home Page](index.html)

## Code Change #1: new-file-2.md
Code change difference on Github:
![Code change for new-file-2.md](/assets/week-4-images/image1.png)

Link to failure-inducing file: [new-file-2.md](https://github.com/justin-chiang/markdown-parser/blob/main/new-file-2.md?plain=1)

Symptom (output) of new-file-2.md as input for failing version of MarkdownParse.java:

Exception in thread "main" java.lang.StringIndexOutOfBoundsException: begin 0, end -1, length 207
        at java.base/java.lang.String.checkBoundsBeginEnd(String.java:4601)
        at java.base/java.lang.String.substring(String.java:2704)
        at MarkdownParse.getLinks(MarkdownParse.java:19)
        at MarkdownParse.main(MarkdownParse.java:30)

Description:

The file new-file-2.md does not contain any links in the file, which causes a bug as the index of both parenthesis and square brackets do not exist, and so the substring using those indexes is invalid. The symptom of the bug is that a StringIndexOutOfBoundsException is thrown, as shown above. To fix this, I added a conditional to check if any of the indexes of the opening/closing of either parenthesis or square brackets is equal to -1, the program breaks out of the while loop.

## Code Change #2: new-file-3.md
Code change difference on Github:
![Code change for new-file-3.md](/assets/week-4-images/image2.png)

Link to failure-inducing file: [new-file-3.md](https://github.com/justin-chiang/markdown-parser/blob/main/new-file-3.md?plain=1)

Symptom (output) of new-file-3.md as input for failing version of MarkdownParse.java:

[]

Description:

The file new-file-3.md contains parenthesis but not square brackets, which causes a bug as the index of parenthesis is dependent on the index of the square brackets, but is not applicable as square brackets do not exist in the file. The symptom of the bug is that the returned list of links is empty. To fix this, I added an if else statement to check that if square brackets do not exist, the program should only consider the indexes of the opening/closing parenthesis; otherwise, consider indexes of both parenthesis and square brackets.

## Code Change #3: new-file-4.md
Code change difference on Github:
![Code change for new-file-4.md](/assets/week-4-images/image3.png)

Link to failure-inducing file: [new-file-4.md](https://github.com/justin-chiang/markdown-parser/blob/main/new-file-4.md?plain=1)

Symptom (output) of new-file-4.md as input for failing version of MarkdownParse.java:

[,]

Description:

The file new-file-4.md contains both square brackets and parenthesis, but there are no links in between the parenthesis, which causes a bug as an empty string is added to the returned list for parenthesis without links inside of them. The symptom of the bug is that the returned list of links is not empty, but a list of empty strings. To fix this, I added an if statement to check that if the length of the substring between the parenthesis is 0, the program should not add the substring to the returned list.

[Back to Home Page](index.html)
