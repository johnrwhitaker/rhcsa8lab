# RHCSA 8 Lab Steps

## Level 1

<details>
  <summary>1. Set the root password to "rootpassword"</summary>
  <code>
    sudo passwd root<br/>
    rootpassword<br/>
  </code>
</details>

<details>
  <summary>2. Create a user "tempuser" with the password "temppassword"</summary>
  <code>
    useradd tempuser<br/>
    passwd tempuser<br/>
    temppassword<br/>
  </code>
</details>

***

## Level 2

<details>
  <summary>3. Locate the man page thst shows how to set a password</summary>
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
  <summary>4. As root, create a user named "testuser" using the man page for <code>useradd</code> as reference</summary>
  <code>useradd testuser</code>
</details>

<details>
  <summary>5. Set the password for "testuser" to "password"</summary>
  <code>
    passwd testuser<br/>
    New password: password<br/>
    BAD PASSWORD: The password fails the dictionary check - it is based on a dictionary word<br/>
    Retype new password: password<br/>
    passwd: all authentication tokens updated successfully.
  </code>
</details>

<details>
  <summary>6. Use globbing to show everything in /etc that have a number in their name (use <code>cd /etc</code> to make /etc your current directory)</summary>
  <code>
    cd /etc<br/>
    ls -d *[0-9]*
  </code>
</details>

<details>
  <summary>7. Use <code>ls -l</code> with a pipe to display results page by page. Then use <code>cd</code> without any arguments</summary>
  <code>
    ls -l | less<br/>
    cd
  </code>
</details>

<details>
  <summary>8. Use vim to create a file named "users" and make sure it contains the names Trevor, Stephen, John, Joe and Hillary</summary>
  <code>
    vim users
  </code>
</details> 

***

## Level 3

<details>
  <summary>9. Create the following directories: /tmp/files/pictures, /tmp/files/photos and /tmp/files/videos</summary>
  <code>mkdir -p /tmp/files/pictures /tmp/files/photos /tmp/files/videos</code><br/>
  The <code>-p</code> option ensures that any subfolders that do not exist get created
</details>

<details>
  <summary>10. Copy all files that have a name starting with a, b, or c from /etc to /tmp/files</summary>
  <code>cp /etc/[a-c]* /tmp/files</code><br/>
  There will be an warning that some subdirectories were not copied because the <code>-r</code> option was not used. This is expect as we only want the files.
</details>

<details>
  <summary>11. Move all files that have a name starting with a or b from /tmp/files to /tmp/files/photos</summary>
  <code>
    cd /tmp/files/<br/>
    mv [ab]* photos/
  </code>
</details>

<details>
  <summary>12. Move all files that have a name starting with c from /tmp/files to /tmp/files/videos</summary>
  <code>mv c* videos/</code>
</details>

<details>
  <summary>13. Copy all files that have a size smaller than 1000 bytes from /etc to /tmp/files/pictures</summary>
  <code>find /etc -size -1000c -exec cp {} pictures \;</code>
</details>

<details>
  <summary>14. Create a symbolic link to /var in /tmp/files</summary>
  <code>ln -s /var .</code>
</details>

<details>
  <summary>15. Create a compressed archive file of the /home directory</summary>
  <code>tar cJvf home.tar.xz /home</code>
</details>

<details>
  <summary>16. Extract the compressed archive with relative file names in /tmp/archive</summary>
  <code>mkdir /tmp/archive; tar xvf home.tar.xz -C /tmp/archive/</code>
</details>

***

## Level 4



***

## Level 5
