# RHCSA 8 Lab Steps

## Level 1

<details>
  <summary>1. Set the root password to "rootpassword"</summary>
  <code>sudo passwd root</code><br/>
  <code>rootpassword</code>
</details>

<details>
  <summary>2. Create a user "tempuser" with the password "temppassword"</summary>
  <code>useradd tempuser</code><br/>
  <code>passwd tempuser</code><br/>
  <code>temppassword</code>
</details>


<details>
  <summary>3. Modify your shell environment so that on every subshell that is started, a variable is set. The name of the variable should be <b>COLOR</b>, and the value should be set to <b>red</b>. Verify that it is working.</summary>
</details>

<details>
  <summary>4. Use the appropriate tools to find the command that you can use to set the system time 1 minute ahead.</summary>
</details>

<details>
  <summary>5. From your home directory, type the command <code>ls -al wergihl *</code> and ensure that errors as well as regular output are redirected to a file with the name /tmp/lsoutput.</summary>
</details>

***

## Level 2

<details>
  <summary>6. Locate the man page thst shows how to set a password</summary>
  <code>man -k password</code><br/>
  There are far to many results here to find what is needed<br/>
  <code>man -k password | grep 1</code><br/>
  Checking general commands to see if anything is applicable<br/>
  <code>man -k password | grep 8</code><br/>
  Checking system administration commands to see if anything is applicable<br/>
  <code>man useradd</code><br/>
  Checking an already known command to see if there's anything that can be used (check see also section)<br/>
  <code>man passwd</code><br/>
  Both command and description don't include the word "password" which is why they weren't found<br/>
</details>

<details>
  <summary>7. As root, create a user named "testuser" using the man page for <code>useradd</code> as reference</summary>
  <code>useradd testuser</code>
</details>

<details>
  <summary>8. Set the password for "testuser" to "password"</summary>
  <code>passwd testuser</code><br/>
  <code>New password: password</code><br/>
  <code>BAD PASSWORD: The password fails the dictionary check - it is based on a dictionary word</code><br/>
  <code>Retype new password: password</code><br/>
  <code>passwd: all authentication tokens updated successfully.</code>
</details>

<details>
  <summary>9. Use globbing to show everything in /etc that have a number in their name (use <code>cd /etc</code> to make /etc your current directory)</summary>
  <code>cd /etc</code><br/>
  <code>ls -d *[0-9]*</code>
</details>

<details>
  <summary>10. Use <code>ls -l</code> with a pipe to display results page by page. Then use <code>cd</code> without any arguments</summary>
  <code>ls -l | less</code><br/>
  <code>cd</code>
</details>

<details>
  <summary>11. Use vim to create a file named "users" and make sure it contains the names Trevor, Stephen, John, Joe and Hillary</summary>
  <code>vim users</code>
</details> 

***

## Level 3

<details>
  <summary>12. Create the following directories: /tmp/files/pictures, /tmp/files/photos and /tmp/files/videos</summary>
  <code>mkdir -p /tmp/files/pictures /tmp/files/photos /tmp/files/videos</code><br/>
  The <code>-p</code> option ensures that any subfolders that do not exist get created
</details>

<details>
  <summary>13. Copy all files that have a name starting with a, b, or c from /etc to /tmp/files</summary>
  <code>cp /etc/[a-c]* /tmp/files</code><br/>
  There will be an warning that some subdirectories were not copied because the <code>-r</code> option was not used. This is expect as we only want the files.
</details>

<details>
  <summary>14. Move all files that have a name starting with a or b from /tmp/files to /tmp/files/photos</summary>
  <code>cd /tmp/files/</code><br/>
  <code>mv [ab]* photos/</code>
</details>

<details>
  <summary>15. Move all files that have a name starting with c from /tmp/files to /tmp/files/videos</summary>
  <code>mv c* videos/</code>
</details>

<details>
  <summary>16. Copy all files that have a size smaller than 1000 bytes from /etc to /tmp/files/pictures</summary>
  <code>find /etc -size -1000c -exec cp {} pictures \;</code>
</details>

<details>
  <summary>17. Create a symbolic link to /var in /tmp/files</summary>
  <code>ln -s /var .</code>
</details>

<details>
  <summary>18. Create a compressed archive file of the /home directory</summary>
  <code>tar cJvf home.tar.xz /home</code>
</details>

<details>
  <summary>19. Extract the compressed archive with relative file names in /tmp/archive</summary>
  <code>mkdir /tmp/archive; tar xvf home.tar.xz -C /tmp/archive/</code>
</details>

<details>
  <summary>20. Log in as user root. In the home directory of root, create one archive file that contains the contents of the /home directory and the /etc directory. Use the name /root/essentials.tar for the archive file.</summary>
</details>

<details>
  <summary>21. Copy this archive to the /tmp directory. Also create a hard link to this file in the / directory.</summary>
</details>

<details>
  <summary>22. Rename the file /essentials.tar to /archive.tar.</summary>
</details>

<details>
  <summary>23. Create a symbolic link in the home directory of the user root that refers to /archive.tar. Use the name link.tar for the symbolic link.</summary>
</details>

<details>
  <summary>24. Remove the file /archive.tar and see what happened to the symbolic link. Remove the symbolic link also.</summary>
</details>

<details>
  <summary>25. Compress the /root/essentials.tar file.</summary>
</details>

***

## Level 4

<details>
  <summary>26. Use head and tail to display the fifth line of the file /etc/passwd</summary>
  <code>head -n 5 /etc/passwd | tail -n 1</code>
</details>

<details>
  <summary>27. Use sed to display the fifth line of the file /etc/passwd</summary>
  <code>sed -n 5p /etc/passwd</code>
</details>

<details>
  <summary>28. Use awk in a pipe to filter the last column out of the results of the command <code>ps aux</code></summary>
  <code>ps aux | awk '{ print $NF }'</code>
</details>

<details>
  <summary>29. Use grep to show all files in /etc that have lines that contain the text 'root' as a word</summary>
  <code>cd /etc</code><br/>
  <code>grep 'root' * 2>/dev/null</code>
</details>

<details>
  <summary>30. Use grep to show all lines from all files in /etc that contain exactly 3 characters</summary>
  <code>grep '^...$' * 2>/dev/null</code>
</details>

<details>
  <summary>31. Use grep to find all files that contain the string "alex", but make sure that "alexander" is not included in the result</summary>
  <code>grep '^alex$' * or grep '\<alex\>'</code>
</details>

<details>
  <summary>32. Describe two ways to show line 5 from the /etc/passwd file.</summary>
</details>

<details>
  <summary>33. How would you locate all text files on your server that contain the current IP address? Do you need a regular expression to do this?</summary>
</details>

<details>
  <summary>34. You have just used the sed command that replaces all occurrences of the text Administrator with root. Your Windows administrators do not like that very much. How do you revert?</summary>
</details>

<details>
  <summary>35. Assuming that in the ps aux command the fifth line contains information about memory utilization, how would you process the output of that command to show the process that has the heaviest memory utilization first in the results list?</summary>
</details>

<details>
  <summary>36. Which command enables you to filter the sixth column of ps aux output?</summary>
</details>

<details>
  <summary>37. How do you delete the sixth line from the file ~/myfile?</summary>
</details>

***

## Level 5

<details>
  <summary>38. Set up SSH-based authentication on server1 and then from server2 SSH to connect to server1</summary>
</details>

***

## Level 6
