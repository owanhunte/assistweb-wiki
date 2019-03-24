<!-- TITLE: Compress and Extract Files Using Linux tar Command -->

The GNU tar command included with Linux distributions has integrated compression. It can create a .tar archive and then compress it with gzip or bzip2 compression in a single command, resulting in a .tar.gz file or .tar.bz2 file respectively.
# Compress an Entire Directory or a Single File
Use the following command to compress an entire directory or a single file on Linux. It works recursively, compressing every other directory inside the directory you specify.


```bash
tar -czvf name-of-archive.tar.gz /path/to/directory-or-file
```


Here's what the options above mean:

* -c: Create an archive.
* -z: Compress the archive with gzip.
* -v: Display progress in the terminal while creating the archive, also known as verbose mode. The v is always optional in these commands, but it can be helpful.
* -f: Allows you to specify the filename of the archive.

For example, say you have a directory named **atlantis** in the current directory and you want to compress and save it to a file named **atlantis.tar.gz**. You can accomplish this by running the following command:


```bash
tar -czvf atlantis.tar.gz atlantis
```
 
# Compress Multiple Directories or Files at Once
The **tar** command can also be used to compress multiple directories, multiple individual files, or both. Just provide a list of files or directories instead of a single one. For example:

```bash
tar -czvf archive.tar.gz /path/to/directory-or-file /path/to/another-directory-or-file /path/to/yet-another-directory-or-file
```

Just list as many directories or files as you want to back up.

# Exclude Directories and Files
In some cases, you may wish to compress an entire directory, but exclude certain files and/or directories. You can do so by appending an *--exclude* switch for each directory or file you want to exclude. For example:


```bash
tar -czvf archive.tar.gz /path/to/directory --exclude=/path/to/directory/subdirectory
```


The *--exclude* switch is very powerful. It doesn’t take names of directories and files, it actually accepts patterns. For example, you could archive an entire directory and exclude all .mp4 files with the following command:


```bash
tar -czvf archive.tar.gz /path/to/directory --exclude=*.mp4
```

# Use bzip2 Compression Instead
While gzip compression is most frequently used to create .tar.gz or .tgz files, tar also supports bzip2 compression. This allows you to create bzip2-compressed files, often named .tar.bz2, .tar.bz, or .tbz files. To do so, just replace the *-z* for gzip in the tar commands with a *-j* for bzip2.

Gzip if faster, but it generally compresses a bit less, so you get a somewhat larger file. Bzip2 is slower, but it compresses a bit more, so you get a somewhat smaller file. Gzip is also more common, with some stripped-down Linux systems including gzip support by default, but not bzip2 support. In general, though, gzip and bzip2 are practically the same thing and both will work similarly.

For example, say we wanted to compress our atlantis directory from our above example using bzip2 compression instead of gzip, our command would look like the following:


```bash
tar -cjvf atlantis.tar.bz2 atlantis
```

# Extract an Archive
The following command would extract the contents of archive.tar.gz to the current directory:


```bash
tar -xzvf archive.tar.gz
```


The *-x* switch replaces the *-c* switch from the compress command, and it specifies that you want to extract an archive instead of create one.

You may want to extract the contents of the archive to a specific directory. You can do so by appending the *-C* switch to the end of the command. For example, the following command will extract the contents of the archive.tar.gz file to the /tmp directory:


```bash
tar -xzvf archive.tar.gz -C /tmp
```

If the file is a bzip2-compressed file, replace the “z” in the above commands with a “j”.

This is the simplest possible usage of the tar command. The command includes a large number of additional options. For more information run the **info tar** command at the shell to view the tar command’s detailed information page. Press the **q** key to quit the information page when you’re done. There is also an [online manual](https://www.gnu.org/software/tar/manual/tar.html) available at GNU's official website. On Windows, you can extract and create .tar archives with the free [7-Zip](https://www.7-zip.org/) utility.