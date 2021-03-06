# CSE 15L Week 2 Lab Report

## Andrew Dai A16366706
---

## (1) **Installing VScode**
- VScode should be free to download by anybody. You can go to their [site](https://raw.code.visualstudio.com/) and click the "download" button. Then, click the relavant download button for your operating system (windows, mac, linux). The download then should be automatic.
![VScode Download](vscode.png)

## (2) **Remotely Connecting**
- You can remotely connect to the ieng6 server using the ssh command in your terminal. Your email to sign in starts with `cs15lwi22` followed by your personal code, plus `@ieng6@ucsd.edu`. The course specific code can be found at [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php), where you can create your password. Then, you can sign in to the server with the password.

![login](ssh.png)

## (3) **Commands**
There are several commands you can try in the remote server. Commands you can try are:
- `cd ~`
- `cd`
- `ls -lat`
- `ls -a`

![example command](command.png)

## (4) **Moving Files**
You can move files over SSH with the scp command, using `scp [file] cs15lwi22[]@ieng6.ucsd.edu:~/`. In the image, I uploaded a java file called "WhereAmI" into the server.

![uploaded](upload.png)

## (5) **Speeding up scp**
Each time we use scp, it prompts a password. We can get an SSH key to speed up the uploading process. The command is `ssh-keygen`.
![key created](key.png)

## (6) Optimizing Remote Running
There are a few ways to make remote running better and easier. For example, you can run multiple commands at the same time by separating them with semicolons.
If this socrtcut is used, running a javac java command together only needs two keystrokes: up and enter in the terminal. However, running a javac and java command separately needs 6 keystrokes: up, up, enter to go javac, and up, up, enter again to go java. Using this semicolon method reduces keystrokes to 1/3!

![javac and java](2commands.png)
