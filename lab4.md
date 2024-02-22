# Lab Report 4
#### Anthony Tong, CSE 15L | PID A17720195

## Tasks Speedrun

### Log into ieng6

With ssh key already setup, you should just be able to ssh in. Type:
```
$ ssh a8tong@ieng6.ucsd.edu<enter>
```

On my screen, the following is the result:
```
atong@MacBook-Pro-121 lab7 % ssh a8tong@ieng6.ucsd.edu
Last login: Thu Feb 22 14:35:37 2024 from 100.81.34.41
quota: Cannot resolve mountpoint path /home/linux/dsmlp/.snapshot/daily.2024-01-12_0010: Stale file handle
quota: Cannot resolve mountpoint path /home/linux/ieng6/cs120wi24/cs120wi24dx/.snapshot/hourly.2024-01-29_1201: Stale file handle
quota: Cannot resolve mountpoint path /home/linux/dsmlp/.snapshot/daily.2024-02-04_0010: Stale file handle
quota: Cannot resolve mountpoint path /home/linux/dsmlp/.snapshot/daily.2024-02-05_0010: Stale file handle
Hello a8tong, you are currently logged into ieng6-201.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   14:40:01   19  0.87,  0.48,  0.41
ieng6-202   14:40:01   12  0.40,  0.20,  0.20
ieng6-203   14:40:01   15  0.28,  1.34,  1.22

 

To begin work for one of your courses [ cs15lwi24 ], type its name 
at the command prompt.  (For example, "cs15lwi24", without the quotes).

To see all available software packages, type "prep -l" at the command prompt,
or "prep -h" for more options.
[a8tong@ieng6-201]:~:104$
```

### Clone your fork of the repository from your Github account

Then we need to clone the fork. Head over to the repo and copy the ssh git link:

![Screenshot 1](images/lab4-ss1.png)

Then we can type the following:
```
$ git clone <ctrl+V> <enter>
```

The following is the result.
```
[a8tong@ieng6-201]:~:104$ git clone git@github.com:atong28/lab7.git
Cloning into 'lab7'...
remote: Enumerating objects: 61, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 61 (delta 0), reused 1 (delta 0), pack-reused 60
Receiving objects: 100% (61/61), 376.61 KiB | 1.51 MiB/s, done.
Resolving deltas: 100% (23/23), done.
[a8tong@ieng6-201]:~:105$
```

### Run the tests, demonstrating that they fail

We need to `cd` into the directory now, and then compile and run the tests. We can copy paste the java compile&run commands beforehand: `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java && java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` so that it's a one-liner for our use later.

Type:
```
$ cd lab7 <enter>
$ <ctrl+V> <enter>
```

This should be the result:
```
[a8tong@ieng6-201]:~:105$ cd lab7
[a8tong@ieng6-201]:lab7:109$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java && java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
JUnit version 4.13.2
..E
Time: 0.519
There was 1 failure:
1) testMerge2(ListExamplesTests)
org.junit.runners.model.TestTimedOutException: test timed out after 500 milliseconds
	at ListExamples.merge(ListExamples.java:44)
	at ListExamplesTests.testMerge2(ListExamplesTests.java:19)

FAILURES!!!
Tests run: 2,  Failures: 1

[a8tong@ieng6-201]:lab7:110$
```

### Edit the code file to fix the failing test

We now need to edit the file, and we previously found that the fastest sequence for this specific file is to type `43j1er2:x` (i.e. go down 43 lines, go to the end of the first word, replace mode and replace with 2, and then save+exit.) Here is our input:

```
$ vim Lis<tab>.java<enter>
43j1er2:x<enter>
```

And our result:
```
[a8tong@ieng6-201]:lab7:110$ vim ListExamples.java
[a8tong@ieng6-201]:lab7:111$
```

Of course, we can't see our changes in stdout after exiting vim, but we have made the changes. Now we can press up arrow twice to use the previous set of commands and execute the java tests:

```
$ <up><up><enter>
```

### Run the tests, demonstrating that they now succeed

And our result:
```
[a8tong@ieng6-201]:lab7:111$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java && java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
JUnit version 4.13.2
..
Time: 0.012

OK (2 tests)

[a8tong@ieng6-201]:lab7:112$
```

### Commit and push the resulting change to your Github account

Cool! Now our tests are running. To add the file to the commit we can just type
```
$ git add Lis<tab><enter>
```

And we see the following in the command line:
```
[a8tong@ieng6-201]:lab7:115$ git add ListExamples.java 
[a8tong@ieng6-201]:lab7:116$
```

Then we need to make the commit, typing
```
$ git commit -m bugfix
```

And we see the following result:
```
[a8tong@ieng6-201]:lab7:117$ git commit -m bugfix
[main 3aead67] bugfix
 Committer: Anthony Tong <a8tong@ieng6-201.ucsd.edu>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+), 1 deletion(-)
[a8tong@ieng6-201]:lab7:118$
```

All that's left is to push it!
```
$ git push
```

```
[a8tong@ieng6-201]:lab7:118$ git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 293 bytes | 293.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:atong28/lab7.git
   ef5285c..3aead67  main -> main
[a8tong@ieng6-201]:lab7:119$
```
