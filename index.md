# Lab Report 4

## Step 4

<img width="402" alt="image" src="https://user-images.githubusercontent.com/98483167/221781592-bfbaf887-46eb-4dfc-95d4-dc6121518f5a.png">

Ssh, or Secure Shell, lets me log into my virtual machine in the ucsd servers.

Keys pressed: `<up> <enter>`

The `ssh cs15lwi23adz@ieng6.ucsd.edu` command was the only command in my local terminal history

## Step 5

<img width="403" alt="image" src="https://user-images.githubusercontent.com/98483167/221781974-3b391f1e-c272-498b-81cd-5bceb891e9ac.png">

This command cloned to github repository into my server's directory. I cloned my lab7 repository from my github account.

Keys pressed: `<Ctrl-r> <cl> <enter>`

The `git clone https://github.com/BlazingTomato/lab7` command was found by going into my bash history and finding the clone command.


## Step 6

<img width="405" alt="image" src="https://user-images.githubusercontent.com/98483167/221783271-38bfb670-a0e9-45ce-838a-a9c16e332c02.png">

The first command compiles the JUnit file into a class file, and then the second command runs the JUnit tests in ListExamplesTests.

Keys pressed: `<Ctrl-r> <javac> <enter> <Ctrl-r> <J> <enter>`

The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command and the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore` command were both accessed through the bash history.

## Step 7

<img width="403" alt="image" src="https://user-images.githubusercontent.com/98483167/221783419-b92ddd9a-79d3-47e4-b65e-e5e5d3a2583d.png">

`vi ListExamples.java` works similar to the `nano` command in that it opens an editor in the terminal.  After that, pressing 'i' enables me to edit the file. After changing the code, 'esc' opens the menu and 'ZZ' saves and exits the editor.

Keys pressed: `<Ctrl-r> <vi> <enter> <i> (changed code) <esc> <ZZ>`

The code was edited by using the vi editor in my terminal. The initial command of `vi ListExamples.java` was found through the bash history.

## Step 8
<img width="404" alt="image" src="https://user-images.githubusercontent.com/98483167/221783558-cdcf5284-a1f0-49ee-aca9-9b7725abd7fd.png">

The commands used are the same as Step 6, and simply recompiles and runs the JUnit tests in ListExamplesTests.

Keys pressed: `<up> <up> <enter> <up> <up> <up> <enter>`

Because the javac and java commands were recently used, the `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was 2 up in the search history, so I used up arrow to access it. Then the `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore` command was 3 up in the history, so I accessed it in the same way.

## Step 9

<img width="401" alt="image" src="https://user-images.githubusercontent.com/98483167/221783689-84f5959c-4503-496d-964a-3538541c8f1d.png">

`git add .` stages new files and modifications, without deletions, and `git commit -am "done"` commits with the changes staged in git add. The '-a' simply automatically stages any changed files, and the 'm' adds a commit message, which in this instance is "done".

Keys pressed: `<Ctrl-r> <ad> <enter> <Ctrl-r> <co> <enter>`

The `git add .` and `git commit -am "done"` commands were accessed through my git history.

