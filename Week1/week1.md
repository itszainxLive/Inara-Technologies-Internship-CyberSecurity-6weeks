> **Module 1: Basic IT Training**
>
> **Week 1: Linux Foundations, SSH & Hardening**

![](./media/image1.png){width="5.759027777777778in"
height="1.7159722222222222in"}

**[1.Navigating the command line: pwd, ls, cd, mkdir, touch, cp, mv,
rm]{.underline}**

![](./media/image2.png){width="4.114583333333333in"
height="2.047222222222222in"}

**Commands used :-**

- **PWD** : It shows the path of current working directory .

- **Mkdir** : It is used to make new folder.

- **Ls** : It shows the files and folder present in the
  directory/folder.

- **Cd** : It is used to change directory and go to a specific directory
  .

- **Mkdir and multiple folders name with space** : These are used to
  create multiple directories with one command .

  ![](./media/image3.png){width="3.277083333333333in"
  height="2.720833333333333in"}

<!-- -->

- **Ls -L :** It Shows details like file permissions, owner, size, and
  the date it was last modified.

- **Ls -La:** Work same as Ls -L but it also shows hidden dot files
  which are normally invisible.

- **Touch:** It is used to create a file

- **Cp:** It is used to copy file from one to another.

  ![](./media/image4.png){width="2.973611111111111in"
  height="2.7645833333333334in"}

<!-- -->

- **Mv:** It is used to move file from one place to another / work as
  cut .

- **Rm:** It is used to delete file .

**[2 . Command structure, arguments and options:-]{.underline}**

- **In linux :** command \[options\] \[arguments\]

- **Ls -La /Etc :** It shows every file, hidden file, and detailed
  permission inside the systems /etc configuration directory.

- **Etc Directory:** It holds text files that control how the operating
  system, network, and installed software behave. Like :- Passwd ,
  Shadow , host etc .

![](./media/image5.png){width="4.6715277777777775in"
height="2.4381944444444446in"}

**[3.Absolute vs relative paths; standard directory layout (/etc, /home,
/var, /usr, /tmp)]{.underline}**

- **Absolute path:** It Starts from the root .and works from anywhere in
  the terminal.

  ![](./media/image6.png){width="2.9347222222222222in"
  height="1.5430555555555556in"}

<!-- -->

- **Relative paths:** It Starts from where you are currently standing
  only works if you are already inside /home/kali.

  ![](./media/image7.png){width="3.3965277777777776in"
  height="1.570138888888889in"}

<!-- -->

- **Cd .. :** It is used to go back to parent directory.

  ![](./media/image8.png){width="4.625in" height="1.5909722222222222in"}

<!-- -->

- **Home:** It shows all user accounts on the system. **E.g.**Kali.

- **Var:** It holds files that change all the time while your system is
  running . **E.g.** cache, local.

- **Var/log:** It writes down every single thing that happens on your
  system.

  ![](./media/image9.png){width="4.7555555555555555in"
  height="2.3777777777777778in"}

<!-- -->

- **Usr:** It holds all the applications, programs, and commands
  installed on your computer.

- **Tmp:** It holds files that programs only need to use for a very
  short time.

- **ls -ld /etc /home /var /usr /tmp:** It shows file permissions and
  other data of directories.

4.  **[Input/output redirection and pipes (\>, \>\>,
    \|):-]{.underline}**

    ![](./media/image10.png){width="2.953472222222222in"
    height="3.0729166666666665in"}

- **Echo \> .txt :** create and write into a file.

- **Cat:** It display what is inside a file .

- **Echo \>\> .txt :** Add new text at bottom without erasing .

- **Nano :** It is used to edit file like Notepad.

- **grep -r:** It searchs file containing that word.

  ![](./media/image11.png){width="3.16875in"
  height="2.6305555555555555in"}

- **\|** : using this we can filter lists and Chain commands .

- **ls \| grep txt:** It only show files that contain txt in their name.

- **ls -la \| grep txt:** It shows full details like size, permissions,
  and dates and only show details for the files ending in .txt .

  ------------------------------------------------------------------------

- **ls /etc \| grep conf \| head:** Looks inside the system
  configuration folder (/etc), filters for files containing \"conf\",
  and show you only the first 10 results .

  ------------------------------------------------------------------------

**[5.Environment variables and shell configuration files]{.underline}**

![](./media/image12.png){width="2.9in" height="2.2006944444444443in"}

![](./media/image13.png){width="4.363194444444445in"
height="1.5756944444444445in"}

**ls -l /.bashrc**: It Shows the file details permissions, owner, size,
and date for the .bashrc file hidden inside home directory.

![](./media/image14.png){width="4.371527777777778in"
height="3.183333333333333in"}

**find /etc -type f -name .conf 2\>/dev/null \| head -20:** find conf
file in /etc and show only first 20 results.

**find /etc -type f -name hosts 2\>/dev/null\\:** It is used to find
hosts name folders in /etc.

![](./media/image15.png){width="5.758333333333334in"
height="1.6493055555555556in"}

**[1.Read, write, execute model; octal and symbolic notation
(chmod)]{.underline}**

![](./media/image16.png){width="3.8506944444444446in"
height="2.5868055555555554in"}

- **Chmod +x:** It gives file a permission to execute.

- **Chmod 750 :** It show permissions for owner , group and Other . r =
  4 , w = 2 , x = 1 . By adding these we give permission in octal form.
  So 750 is rwx , rx , 0 .

- **Chmod 444 :** It allow every user to only read the file.

- **./permissions_test.sh :** This command is used to execute the script
  in the file.

  ![](./media/image17.png){width="4.0777777777777775in"
  height="2.7256944444444446in"}

- **Chmod -R :** It is used to give permission to all the files present
  in a folder in a single command.

- **755:** It means owner will be able to read , write and execute , but
  other two will be able to only read and execute it .

**[2.Ownership and group membership (chown, chgrp)]{.underline}**

![](./media/image18.png){width="3.7819444444444446in"
height="2.783333333333333in"}

- **sudo groupadd per_group:** It is used to Add a new group to the
  system.

- **sudo chown \$(whoami):per_group permissions_test.sh:** It chages the
  owner of the file to current user and group to new group that I
  created .

- **sudo chgrp per_group permission:** It changes the ownership of the
  whole folder to a new group .

- **sudo usermod -aG per_group \$(whoami):** It added the current user
  to a new group without deleting the old one.

  ![](./media/image19.png){width="5.757638888888889in"
  height="1.4659722222222222in"}

- **id \$(whoami):** It shows all the details and the groups of the
  current user.

- **Ls -la** : As we can see that the group of the files in thisfolder
  are changed to new group.

**3[.Special bits: setuid, setgid and the sticky bit; the
umask]{.underline}**

![](./media/image20.png){width="3.5in" height="2.8673611111111112in"}

- **Umask :** was used to check the current default permission mask.

- **ls -la:** was used to check the files, folders, permissions, owner,
  and group.

- **chmod 2775 mask:** changed the permissions of the mask directory and
  enabled the setgid bit.

  ![](./media/image21.png){width="3.140972222222222in"
  height="2.423611111111111in"}

- **sudo chgrp per_group mask:** changed the group ownership of the mask
  directory to per_group.

- **ls -la:** was used again to verify the changes.

  ![](./media/image22.png){width="3.640972222222222in"
  height="2.671527777777778in"}

- **mkdir dropbox && sudo chmod 1777 dropbox:** created a dropbox
  directory and enabled the sticky bit with 1777 permissions.

- **ls -ld dropbox:** was used to verify the sticky bit and directory
  permissions.

**[4.Creating and managing users and groups; password and account
aging]{.underline}**

![](./media/image23.png){width="3.8743055555555554in"
height="2.7534722222222223in"}

- **useradd :** create a new user.

- **passwd :** set a password for the new user.

- **id zainuser:** check the user UID, GID, and groups.

- **groups zainuser:** check the groups of the user.

- **cat /etc/passwd \| grep zainuser :** verify the user\'s entry in the
  passwd file.

  ![](./media/image24.png){width="3.8875in"
  height="2.941666666666667in"}

- **sudo chage -l zainuser:** was used to check the password aging
  settings of the user.

- **sudo chage -m 0 zainuser:** set the minimum number of days between
  password changes to 0.

- **sudo chage -l zainuser:** used again to verify the change.

- **sudo chage -E -1 zainuser:** removed the account expiration date.

  .

  ![](./media/image25.png){width="3.6444444444444444in"
  height="0.5548611111111111in"}

- **Userdel:** It delete all the records of the user .

**[5.The sudo model, the sudoers file, and switching users
safely:-]{.underline}**

![](./media/image26.png){width="4.102083333333334in"
height="2.3631944444444444in"}

- **sudo -l :** used to check the sudo permissions of the current user.

- **sudo -i :** used to open a root login shell.

- **sudo su - zainuser :** used to switch to the zainuser account.

  **Scenario 1: World-writable sensitive file fix:**

  ![](./media/image27.png){width="3.863888888888889in"
  height="1.7659722222222223in"}

  First creating a folder name app inside zain_day1 , then creating a
  yml file in it and setting its permission to read and write for All .
  which states the brken state . Now t fix this we have to change its
  permission from 666 to 640 t fix its broken state and only writeable
  by owner .

  **Scenario 2 :missing execute permission:**

  ![](./media/image28.png){width="3.8645833333333335in"
  height="2.203472222222222in"}

  I created a deploy.sh file and added a simple command to print deploy
  running. When I tried to run it, it showed permission denied because
  the file did not have execute permission. I checked the file
  permissions, used chmod +x deploy.sh to give it execute permission,
  and then ran it successfully.
