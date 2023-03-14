# Lab Report 4 With Bash Script

The easiest solution I found to finish lab 4 with a bash script was to first write the script in your local directory.

The script should follow some process like this:

## Step 1

git clone the lab 7 repository. One possible method is

`git clone $1`

with $1 being the argument you pass when running the bash script in the terminal.

## Step 2

Compile and Run the JUnit tests. One possible method is to save the JUnit argument in a variable and then typing the following commands

`javac -cp $CPATH *.java
java -cp $CPATH org.junit.runner.JUnitCore ListExamplesTests > junit-output.txt`


## Step 3

To fix the ListExamples.java so the tests can succeed:

echo the entire edited file in the bash script and redirect the output into ListExamples.java


## Step 4

Copy and paste the commands in Step 2 to recompile the JUnit Tests to show that they run

## Step 5

Put 
`git add .
git commit -am "done"`

To stage the changes and commit into the repository.

## Final

Once that is all typed into your bash script, simply scp, secure copy, the file into your remote account, log into your remote account, and run the script. Technically, since the Timer starts when you log into your ieng6 account, you simply have to run the bash script with the repo. to finish the race instantly. Even faster if you have the command saved in history so you can access it even quicker.

