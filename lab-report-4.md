# Lab Report 7
In this lab report, we will demonstrate how to clone, edit, and commit a file.

## Step 4
I logged into ieng6.
I typed `ssh cs15lwi23USERNAME@ieng6.ucsd.edu` and pressed `<enter>`. Then I entered my password and pressed `<enter>`.
![image](https://user-images.githubusercontent.com/110417529/221437324-cdd45f28-5aa7-460e-9184-efd8cd4c7323.png)


## Step 5

Buttons clicked: `<Ctrl-Shift-v>`

I typed `git clone git@github.com:ucsd-cse15l-w23/lab7.git`, using the copy command for the ssh link.
![image](https://user-images.githubusercontent.com/110417529/221437605-485f5627-0586-43b5-ae59-2f8b88a07f07.png)

## Step 6

Buttons clicked: `<Ctrl-Shift-v><Ctrl-Shift-v>`

1. `cd lab7` : changed directory to lab7
2. `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` : compiled JUnit for testing the file
3. `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` : ran JUnit test on ListExamplesTests.java

![image](https://user-images.githubusercontent.com/110417529/221438135-6ce91898-28c4-4332-b1b1-12793cfab0cf.png)
![image](https://user-images.githubusercontent.com/110417529/221438044-3a6c447d-b785-472d-bf0a-3b20b27c482f.png)

## Step 7

Buttons clicked: `<Ctrl-v><Ctrl-o><Enter><Ctrl-x>`

1. `nano ListExamples.java` : opens up editor for code as seen below

![image](https://user-images.githubusercontent.com/110417529/221439411-9edb6c9b-4119-424b-a3e5-6e00b13a1a79.png)

2. `Ctrl-v` to go onto second page of code

3. Replace erroneous variable `index1` with `index2` as seen below

![image](https://user-images.githubusercontent.com/110417529/221440958-63ee83a9-22b4-47cd-bea9-6b6620d60a9b.png)

4. `Ctrl-o` then `Enter` to save, then `Ctrl-x` to exit.

## Step 8
Buttons clicked: `<Ctrl-Shift-v><Ctrl-Shift-v>`

1. `javac ListExamples.java` : compiling new code
2. `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` : ran JUnit test on ListExamplesTests.java

![image](https://user-images.githubusercontent.com/110417529/221441135-752c7ebe-1eda-4548-a68e-f7dd7478e8ab.png)

## Step 9

Buttons clicked: `<Enter>`

1. `git add ListExamples.java : adds ListExamples.java to the stage to be committed
2. `git commit -m "fixed code" : commits the code with message "fixed code"

![image](https://user-images.githubusercontent.com/110417529/221441770-c333997c-6090-47b6-b415-0f807d207323.png)

The message git gives occurred because I have not set my username and e-mail, so git has to guess what the most likely usernames and emails are. However, the files are indeed committed.
