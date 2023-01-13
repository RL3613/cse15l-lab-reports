# How to log into your CSE15L account

## Step 1: VSCode

VSCode is an IDE which we will use in CSE15L.

If VSCode is not your preferred IDE then too bad.

Go to [VSCode](https://code.visualstudio.com/Download) and download VSCode if you do not have it already.

## Step 2: Git

Git is a version control system, meaning it's a system that saves different versions of a file. It's sort of like Google Drive without the UI, so you have to use commands to do everything.

Go to [git](https://git-scm.com/downloads) to download git.

On VSCode, go to terminal dropdown at the top left and select new terminal.

This will open a new terminal at the bottom.

![image](https://user-images.githubusercontent.com/110417529/212207867-ac84d3b5-c66c-46b9-a363-d0f66011c156.png)
(note this image does not have terminal open)

## Step 3: Getting CSE15L accounts

Go to [login](https://sdacs.ucsd.edu/~icc/index.php).

Use your email and student ID to log into Account Lookup. Then click the button saying cse15lwi23YOURUSERNAME. This button is the name of your CSE15L account.

Click the "change password" button and submit a global password change. Select no for change MyTritonLink password and hit enter after entering the confirm password. Do not click check password. After it is successful, this will be your new CSE15L password.

![image](https://user-images.githubusercontent.com/110417529/212207738-601259b7-de31-4c7f-a92a-a14806e39ac8.png)

## Step 4: Connecting to UCSD Remote Server

In CSE15L, you will need to run code on other computers. Perhaps those computers have software which yours does not. For this purpose, we will connect to a remote server through VSCode.

Open a new terminal and type "`ssh cse15lwi23USERNAME@ieng6.ucsd.edu`" with your username replacing USERNAME. Then, when prompted, type "yes" and fill in your password. Note that your password will not appear in text as you type it in for security.

![image](https://user-images.githubusercontent.com/110417529/212208170-ffdc4a7d-400c-4cec-91a1-8374073c9100.png)

You should see a long message containing notice and system information when you successfully log in.

## Step 5: Trying Commands

Try a few commands after connecting to test that it works!

You can try:
- `cd`
- `pwd`
- `mkdir`
- `ls -lat`
- `ls -a`

![image](https://user-images.githubusercontent.com/110417529/212210105-95717ba5-ee39-4bc3-ba07-67337dbb6b88.png)
