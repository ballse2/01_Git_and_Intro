01_Git_and_Intro
================

Practice with basic git functions, and intro to study of Data Structures

Reading
=======

**Version Control with Git, 2nd Ed**. Loeliger and McCullough. 

http://proquest.safaribooksonline.com/book/databases/content-management-systems/9781449345037/version-control-with-git/id302681?uicode=ohlink (Free access through www.lib.miamioh.edu, but limited to 100 simultaneous users across all OhioLink. I recommend downloading/printing the required readings ahead of time, just in case.)

Read only the following:

1. Chapter 1
  * Background
  * The Birth of Git
2. Chapter 3: Getting Started
  * Intro
  * The Git Command Line
  * Quick Introduction to Using Git (read all sections)
  * Configuration files (Intro only, may skip part on aliases)
3. Chapter 4: Basic Git Concepts
  * Basic concepts (read all)
  * Object store pictures
  * Git concepts at work (read all)
4. Chapter 21: Git and Github
  * Repo for Public Code
  * Creating a GitHub Repository
  * Forks
  * Creating Pull Requests
  * Managing Pull Requests
  * Coding Models

**Open Data Structures in C++**. Morin, edition 0.1G-beta

http://opendatastructures.org/ (Free access. I recommend downloading the PDF version.)

Read the following:

1. Chapter 1 (pp. 1-21)

Homework
========

1. Create an account with github.com. You may select the free account. If you want to get some free private repos, you may apply at https://github.com/edu
2. Go to https://github.com/MiamiOH-CSE274/01_Git_and_Intro and fork the repo, which will create a copy of it in your github account.
3. Install git on your computer, if you do not already have it. I recommend installing http://windows.github.com/ if you use windows, or http://mac.github.com/ if you use Mac. **HOWEVER, I highly recommend using the command-line tools for everything, and ignoring the GUI. I will not be providing help with configuring/using the GUI.**
4. Clone your repo from github to your computer. When you are at the web page for your repo, `https://github.com/[your github id]/01_Git_and_Intro`, you will see info about how to clone it. The easiest way is to go to the command line terminal, and type `git clone git@github.com:[your github id]/01_Git_and_Intro.git`
6. Complete the exercises below by modifying this file.
7. After you complete each answer, be sure to create a new commit with the changes (using `git add README.md` and `git commit -m` as appropriate). Also, be sure to upload to github frequently by using `git push`
8. If I don't see at least 4-5 commits on this homework, I'm going to be unhappy.
9. Once complete, send me a pull request. This is your official "turn in" of the homework, which I will grade.
10. Double check that you did the right thing by going to https://github.com/MiamiOH-CSE274/01_Git_and_Intro/pulls and making sure that your pull request is there, and looks like you expect. Optimism is the root of all evil.

Exercises
=========

#### 1. Based on the reading in the Git book, is it okay to keep your local copy of your repo on a USB drive and just carry it around? Explain why or why not. What about keeping it on the M: drive?

Yes to both. Because Git is all about freedom. A repository also contains all history and revisions of the files as well as the files themselves and a copy of the repository itself, so there is no information lost by keeping just the repository in an isolated environment like the flash drive.

#### 2. Imagine that you come into the lab on the weekend to work on homework with friends, but you forgot to bring your USB drive with your repo on it. What should you do?

Clone your forked repo from Github onto the lab machine and proceed as normal, then push it back to the server at the end.

#### 3. Morin, Exercise 1.1 (p. 25). NOTE: You should not actually implement the solution with code. Instead, explain your solution using English. Pay special attention to explaining which data structure you ought to use, and why.
1. Use a list to store all the lines as they are read in, then use a for loop that runs backwards (i = size of list, i decrementing) to write them out in reverse order.
2. Keep track of current position in a int called pos (initialized at 0). Use a for loop with i < pos+50 to read in the 50 lines and store them in a list, then a reverse for loop like #1 counting down from array size to print them out. Both of those steps are contained in one while loop (while input source has data) it will read the 50 lines, write them in reverse, then update pos + 50 and run the whole loop again provided there are more lines to be read. 
3. Contain all in a while input has next line loop, so that while that is true if line length > 0 it will add each line into a list as they come in. Each line read will also update a pos variable. Else if line length <= 0, print the line accessed by the index pos-42. Update pos +1 and return to the top of the loop. At the top of the loop, there is an if length of list > 42, if so remove the first element. So each time it runs, it removes the first one and adds the new one on the end. 
4. Read input one line at a time and store in a USet, then write that USet back out using a regular for loop.
5. Read lines one at a time and add to a list. As you read in each successive line, foreach your list to see if it already exists, if yes then write it directly to output, not to the list. Then start again with the next line, checking it and writing it to the appropriate location.
6. While loop the input into a SSet, using a compare function that compares lengths. Then use a foreach loop to dump this into a USet, and write out that USet.
7. Do the same thing as six, but skip the dumping into USet step.
8. Store and add each line to a list. Use one for loop such that i =0, i <= length of list, i+2 increment, print list of i index. Then do the same for loop again but i=1, i+2, print out list[i].
9. Read all lines consecutively into a list. I can't think of any way to randomly output all of them, I'm sorry.

#### 4. Your choice: Morin, Exercise 1.2, 1.3, or 1.4 (pick one)

Note: You should not need to write any real computer code for any of these. Instead, explain how you would approach the problem using a combination of English and pseudocode. The goal is to write something that is understandable by any programmer, even if the two of you have never used the same computer language. (In other words, assume the other person does not know the syntax of Java or C/C++, but knows the basic programming constructs such as for loops, if statements, variables, and so on.)

1.4:
Use pop to take the last element off of the stack and use add onto the queue, doing that for all elements will result in them being in the same order as in the original stack. Then from q use remove (which will take the last one) and push it onto the stack s, and do the same with all the rest of the elements, they will end up in reversed order from the original.

#### 5. Define/explain each of the following terms, as they relate to git.

1. blob - "binary large object", used to represent each version of a file. Holds the file's data but no metadata about it or even its name.
2. tree - represents one level of directory information. Records all blob IDs, paths, and some file metadata in that directory in order to build a complete hierarchy of files and subdirectories.
3. commit - contains metadata for each change to the repository that has been staged, including author, committer, commit date and log message. Each commit points to a tree that captures the current state of the repository.
4. repo - short for repository, it's a database containing all the info necessary to retain and manage the revisions and history of a project.
5. hash - SHA1 applied to the contents of the object, yielding a hash value. Also called the object ID, will change with any tiny change to the object which causes versions to be indexed separately.
