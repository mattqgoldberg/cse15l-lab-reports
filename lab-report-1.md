# How to log into a course-specific account on ieng6

## Step 1: Find CSE15L Account

In order to log-in to the server for this lab, you must
set up your course account using the link below.

[https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php)

Go to the link and input our UCSD username and PID.
Take note of your course specific account name for 15L.
(Should start with cs15lwi23)
Mine is cs15lwi23ann.

Then, click on your acccount name and click to link on that page
that says to change your password.

**Read Carefully:**

Enter your current and new password, but do not click check password!
Just hit enter on your keyboard and your password will reset.

Wait 15 minutes before continuing for the password change to take effect.

## Step 2: Install Visual Studio Code

If you do not have it installed go to the link below to install VS Code.

[https://code.visualstudio.com/](https://code.visualstudio.com/)
![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main/img/INSTALL_VSCODE.png?raw=true)
I already used it for CSE 11 so I did not need to do this step.

Click the Blue download button that will download the latest version of VS Code for your machine.

When it finishes downloading, run the installer called VSCodeUserSetup.exe.
Accept the terms and conditions and click next until VS Code installs on your machine.

## Step 3: Install Git and Set Up with VS Code

Go to the link below and install git.
[https://gitforwindows.org/](https://gitforwindows.org/)

Open VS Code.
Then, to use git in VS Code, Press Ctrl + Shift + P to open the command palette.
Type Select Default Profile.
Select Git Bash from the options.
Then click the + sign in the terminal and the new terminal will
be a Git Bash terminal.

## Step 4: Remotely Connect

Type the following into the terminal:

`$ ssh cs15lwi23zz@ieng6.ucsd.edu`

Replace zz with the letters from the username you wrote down earlier.

Type in the new password you created. It is normal for the password to not
appear as you type it.

On your first time connecting you will be asked if you are sure you'd like to
continue connecting.

Type 'yes' and press enter.

Now you are connected to the server and can run commands!

![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main//img/LOGIN.png?raw=true)

## Step 5: Running Commands

There are lots of commands that you could run now that
you have connected but such as cd, ls, pwd, mkdir.

Here are some screenshots of commands that I ran!

![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main/img/COMMANDS.png?raw=true)

The first command the I ran was `pwd` which stands for print working directory. This will
print to the console the path of the working directory.

The second command `ls` prints a list to the console of all the files contained in the working directory.

The command `cd ..` will change the working directory to the parent directory.

Running `pwd` again shows the new working directory has changed.

Typing `cd public` will change the directory to /home/linux/ieng6/cs15lwi23/public.

Running `pwd` again confirms this.

Running `ls` shows the list of files in this directory including hello.txt.

In order to read out hello.txt, we can run `cat hello.txt`, which will print out the
contents of hello.txt to the console.

Thanks for looking at my tutorial!

