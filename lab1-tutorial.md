# How to log into your CSE15L account

## Step 1: VSCode

VSCode is the IDE which we will use in CSE15L. IDE's let you write, run, and debug code.

Go to [VSCode](https://code.visualstudio.com/Download) and download VSCode if you do not have it already. Select the appropriate version for your operating system and click the blue download button as seen in the image below.

![image](https://user-images.githubusercontent.com/110417529/215011739-127146b5-900e-475e-9cae-1afd1eb951a6.png)


## Step 2: Git

Git is a version control system, meaning it's a system that saves different versions of a file. It's sort of like Google Drive without the UI, so you have to use commands to do everything.

Go to [git](https://git-scm.com/downloads) to download git; click the appropriate version for your operating system.

On VSCode, go to terminal dropdown at the top left and select new terminal.

This will open a new terminal at the bottom.

![image](https://user-images.githubusercontent.com/110417529/212207867-ac84d3b5-c66c-46b9-a363-d0f66011c156.png)
(note this image does not have terminal open)

Note: If you want a UI for git, you can download [Github Desktop](https://desktop.github.com/).

## Step 3: Getting CSE15L accounts

Go to [login](https://sdacs.ucsd.edu/~icc/index.php).

Use your email and student ID to log into Account Lookup. Then click the button saying cse15lwi23YOURUSERNAME. This button is the name of your CSE15L account.

Click the "change password" button and submit a global password change. Select no for change MyTritonLink password and hit enter after entering the confirm password. Do not click check password. After it is successful, this will be your new CSE15L password.

![image](https://user-images.githubusercontent.com/110417529/212207738-601259b7-de31-4c7f-a92a-a14806e39ac8.png)

## Step 4: Connecting to UCSD Remote Server

In CSE15L, you will need to run code on other computers. Perhaps those computers have software which yours does not. For this purpose, we will connect to a remote server through VSCode.

Open a new terminal and type 
```console
ssh cse15lwi23USERNAME@ieng6.ucsd.edu
```
with your username replacing USERNAME. Then, when prompted, type "yes" and fill in your password. Note that your password will not appear in text as you type it in for security.

![image](https://user-images.githubusercontent.com/110417529/212208170-ffdc4a7d-400c-4cec-91a1-8374073c9100.png)

You should see a long message containing notice and system information when you successfully log in, like so:

![image](https://user-images.githubusercontent.com/110417529/215013654-638abb48-8263-461d-9553-795e06e6ab88.png)

## Step 5: Trying Commands

Try a few commands after connecting to test that it works!

You can try:
- `cd` : this changes the directory the computer is in (which files the computer currently can access and run).
- `pwd` : this tells you the current directory
- `mkdir` : this creates a new directory, which is like a folder you can add files to
- `ls` : this lists the files under the current directory which you can change directory (`cd`) into
- `ls -a` : this lists all the files under the current directory, even the hidden ones which begin with `.`

![image](https://user-images.githubusercontent.com/110417529/212210105-95717ba5-ee39-4bc3-ba07-67337dbb6b88.png)
