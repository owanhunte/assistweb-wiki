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
The tar command can also be used to compress multiple directories, multiple individual files, or both. Just provide a list of files or directories instead of a single one. For example:

```bash
tar -czvf archive.tar.gz /path/to/directory-or-file /path/to/another-directory-or-file /path/to/yet-another-directory-or-file
```

Just list as many directories or files as you want to back up.