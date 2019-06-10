<!-- TITLE: Create Symbolic Link -->

Symbolic links, also called soft links, are created with the **ln** command. For example, the following would create a symbolic link named *link1* to a file named *file1*, both in the current directory:<br><br>

```batchfile
$ ln -s file1 link1
```
<br>

To verify the new symbolic link run:<br><br>

```batchfile
$ ls -l file1 link1
```
<br>

Sample outputs:<br><br>

```batchfile
-rw-r--r--  1 ubuntu  ubuntu  12 Jun  7 22:01 file1
lrwxr-xr-x  1 ubuntu  ubuntu   5 Jun  7 22:01 link1 -> file1
```
<br>

So the syntax is as follows to create a symbolic link in Unix or Linux, at the shell prompt:<br><br>

```batchfile
$ ln -s {source-filename} {symbolic-filename}
```
<br>

For example the following command creates a symbolic link for `/etc/nginx/sites-available/helpdesk.assistweb.co` as `/etc/nginx/sites-enabled/helpdesk.assistweb.co`. This example requires administrative privileges to run so we use sudo as well:<br><br>

```batchfile
$ sudo ln -s /etc/nginx/sites-available/helpdesk.assistweb.co /etc/nginx/sites-enabled/helpdesk.assistweb.co
```
<br>