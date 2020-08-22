# RHCSA 8 Lab Steps

<details>
  <summary>Set the root password to "rootpassword"</summary>
  
  ```bash
  sudo passwd root
  Changing password fot user root.
  rootpassword
  BAD PASSWORD: The apssword contains the user name in some form
  rootpassword
  ```
  
</details>

<details>
  <summary>Create a user "tempuser" with the password "temppassword"</summary>
  ```bash
  sudo useradd tempuser
  sudo passwd tempuser
  temppassword
  temppassword
  ```
</details>

<details>
  <summary>Use the appropriate tools to find the command that you can use to set the system time 1 minute ahead.</summary>
</details>

<details>
  <summary>From your home directory, type the command <code>ls -al wergihl *</code> and ensure that errors as well as regular output are redirected to a file with the name /tmp/lsoutput</summary>
  <code>ls -al wergihl * &> /tmp/lsoutput</code>
</details>

<details>
  <summary>Locate the man page thst shows how to set a password</summary>
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
  <summary>As root, create a user named "testuser" using the man page for <code>useradd</code> as reference</summary>
  ```bash
  su -
  <i>root password</i>
  useradd testuser
</details>

<details>
  <summary>Set the password for "testuser" to "password"</summary>
  ```bash
  passwd testuser
  New password: password
  BAD PASSWORD: The password fails the dictionary check - it is based on a dictionary word
  Retype new password: password
  passwd: all authentication tokens updated successfully.
  ```
</details>

<details>
  <summary>Use globbing to show everything in /etc that have a number in their name (use <code>cd /etc</code> to make /etc your current directory)</summary>
  ```bash
  cd /etc
  ls -d *[0-9]*
  ```
</details>

<details>
  <summary>Use <code>ls -l</code> with a pipe to display results page by page. Then use <code>cd</code> without any arguments</summary>
  ```bash
  ls -l | less
  cd
  ```
</details>

<details>
  <summary>Use vim to create a file named "users" and make sure it contains the names Trevor, Stephen, John, Joe and Hillary</summary>
  <code>vim users</code>
</details> 

<details>
  <summary>Create the following directories: /tmp/files/pictures, /tmp/files/photos and /tmp/files/videos</summary>
  <code>mkdir -p /tmp/files/pictures /tmp/files/photos /tmp/files/videos</code><br/>
  The <code>-p</code> option ensures that any subfolders that do not exist get created
</details>

<details>
  <summary>Copy all files that have a name starting with a, b, or c from /etc to /tmp/files</summary>
  <code>cp /etc/[a-c]* /tmp/files</code><br/>
  There will be an warning that some subdirectories were not copied because the <code>-r</code> option was not used. This is expect as we only want the files.
</details>

<details>
  <summary>Move all files that have a name starting with a or b from /tmp/files to /tmp/files/photos</summary>
  ```bash
  cd /tmp/files/
  mv [ab]* photos/
  ```
</details>

<details>
  <summary>Move all files that have a name starting with c from /tmp/files to /tmp/files/videos</summary>
  <code>mv c* videos/</code>
</details>

<details>
  <summary>Copy all files that have a size smaller than 1000 bytes from /etc to /tmp/files/pictures</summary>
  <code>find /etc -size -1000c -exec cp {} pictures \;</code>
</details>

<details>
  <summary>Create a symbolic link to /var in /tmp/files</summary>
  <code>ln -s /var .</code>
</details>

<details>
  <summary>Create a compressed archive file of the /home directory</summary>
  <code>tar cJvf home.tar.xz /home</code>
</details>

<details>
  <summary>Extract the compressed archive with relative file names in /tmp/archive</summary>
  <code>mkdir /tmp/archive; tar xvf home.tar.xz -C /tmp/archive/</code>
</details>

<details>
  <summary>Log in as user root. In the home directory of root, create one archive file that contains the contents of the /home directory and the /etc directory. Use the name /root/essentials.tar for the archive file.</summary>
</details>

<details>
  <summary>Copy this archive to the /tmp directory. Also create a hard link to this file in the / directory.</summary>
</details>

<details>
  <summary>Rename the file /essentials.tar to /archive.tar.</summary>
</details>

<details>
  <summary>Create a symbolic link in the home directory of the user root that refers to /archive.tar. Use the name link.tar for the symbolic link.</summary>
</details>

<details>
  <summary>Remove the file /archive.tar and see what happened to the symbolic link. Remove the symbolic link also.</summary>
</details>

<details>
  <summary>Compress the /root/essentials.tar file.</summary>
</details>

<details>
  <summary>Use head and tail to display the fifth line of the file /etc/passwd</summary>
  <code>head -n 5 /etc/passwd | tail -n 1</code>
</details>

<details>
  <summary>Use sed to display the fifth line of the file /etc/passwd</summary>
  <code>sed -n 5p /etc/passwd</code>
</details>

<details>
  <summary>Use awk in a pipe to filter the last column out of the results of the command <code>ps aux</code></summary>
  <code>ps aux | awk '{ print $NF }'</code>
</details>

<details>
  <summary>Use grep to show all files in /etc that have lines that contain the text 'root' as a word</summary>
  <code>cd /etc</code><br/>
  <code>grep 'root' * 2>/dev/null</code>
</details>

<details>
  <summary>Use grep to show all lines from all files in /etc that contain exactly 3 characters</summary>
  <code>grep '^...$' * 2>/dev/null</code>
</details>

<details>
  <summary>Use grep to find all files that contain the string "alex", but make sure that "alexander" is not included in the result</summary>
  <code>grep '^alex$' * or grep '\<alex\>'</code>
</details>

<details>
  <summary>Describe two ways to show line 5 from the /etc/passwd file.</summary>
</details>

<details>
  <summary>How would you locate all text files on your server that contain the current IP address? Do you need a regular expression to do this?</summary>
</details>

<details>
  <summary>You have just used the sed command that replaces all occurrences of the text Administrator with root. Your Windows administrators do not like that very much. How do you revert?</summary>
</details>

<details>
  <summary>Assuming that in the ps aux command the fifth line contains information about memory utilization, how would you process the output of that command to show the process that has the heaviest memory utilization first in the results list?</summary>
</details>

<details>
  <summary>Which command enables you to filter the sixth column of ps aux output?</summary>
</details>

<details>
  <summary>How do you delete the sixth line from the file ~/myfile?</summary>
</details>

<details>
  <summary>Set up SSH-based authentication on server1 and then from server2 SSH to connect to server1</summary>
</details>

<details>
  <summary>
    Modify the environment so that the following settings are available to all users:
    * An alias named <code>ipconfig</code> that runs the <code>ip addr show</code> command
    * A variable with the name <code>COLOR</code> that is set the the value <code>red</code>
    * Ensure the alias is available in subshells too
  </summary>
  ```bash
  su -
  cd /etc/profile.d/
  vim labenv.sh
  i
  alias ipconfig='ip addr show'
  export COLOR=red
  esc
  :wq
  ```

  Nothing else to do since aliases are already available in subshells by default. The variable will also be available since it was created with <code>export</code>.
</details>

<details>
  <summary>
    Create 4 users: <code>john</code>, <code>paul</code>, <code>george</code>, and <code>ringo</code><br/>
    Set their passwords to expire after 60 days<br/>
    Create a group <code>writers</code> and make <code>john</code> and <code>paul</code> members of that group<br/>
    Create a group <code>guitarists</code> and make <code>george</code> a member of that group<br/>
    Create a group <code>drummers</code> and make <code>ringo</code> a member of that group<br/>
    Create a group <code>band</code> and make all four users a member of that group as a secondary group<br/>
    Use input redirection to set the password for these users to <code>password</code><br/>
    Ensure all these users get a home directory in <code>/home</code>
  </summary>
  <br/>
  The most efficient way to tackle these tasks is not in the order presented

  ```bash
  vim /etc/login.defs
  i
  PASS_MAX_DAYS 60
  *esc*
  :wq
  
  vim /etc/default/useradd
  i
  HOME=/home
  *esc*
  :wq

  groupadd writers
  groupadd drummers
  groupadd band

  useradd -G writers, band john
  useradd -G writers, band paul
  useradd -G guitarists, band george
  useradd -G drummers, band ringo

  for i in john paul george ringo; do echo password | passwd --stdin $i; done
  ```

  If any of the users were already created you would use:

  ```bash
  usermod -aG *GROUPNAME*... *USERNAME*
  ```
  
  The -a is for append, without this the groups will be overwritten with what is listed
</details>

<details>
  <summary>
    Ensure that files create by user <code>root</code> cannot be acccessed by group or others; files of ordinary users should be readable by the group owners<br/>
    Create the directories <code>/data/writers</code> and <code>/data/drummers</code><br/>
    Members of the group <code>writers</code> should be able to read and write files in <code>/data/writers</code>, members of the group <code>drummers</code> should be able to read and write files in <code>/data/drummers</code><br/>
    No other users should have access to these directories<br/>
    Users will only be allowed to delete files they have created themselves, but user <code>john</code> is the lead writer and should be able to manage all writers files
  </summaary>

  ```bash
  umask 077
  touch anewfile
  las -l anewfile

  mkdir -p /data/writers /data/drummers

  cd /data
  ls -l
  chgrp writers writers
  chmod g+rwx writers
  chgrp drummers drummers
  chmod g+rwx drummers
  ls -l

  chmod +t writers
  chown john writers
  ```

</details>

<details>
  <summary>
    Ensure that others are denied default permissions to any file user <code>paul</code> creates<br/>
    Create a shared group directory structure <code>/data/profs</code> and <code>/data/students</code>
    <ul>
      <li>Members of the groups have full read and write access to their directories, others has no permissions at all
      <li>Files creatd in these directories are writeable for all members of the group
      <li>Users can only delete files they have created themselves
      <li>Members of group <code>profs</code> have read access to everything in <code>/data/students</code>
      <li>User <code>john</code> is headmaster and should be able to delete everything in <code>/data/students</code> and <code>/data/profs</code>
    </ul>
  </summary>

  ```bash
  cd /home/paul/
  ls -a
  vim .bash_profile

  i
  umask 007
  *esc*
  :wq

  su - paul
  touch -l paul5
  ls -l paul5
  logout

  cd /data
  mkdir profs students
  ls -l

  chmod 3770 students/

  chown john:students students/
  chown john:profs profs/
  ls -lk

  cd students/
  ls -l
  setfacl -m d:g:profs:rx /data/students
  getfacl .
  ```
</details>