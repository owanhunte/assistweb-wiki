<!-- TITLE: Frequently Used Commands -->
# git checkout for Remote Branches
The syntax for making git checkout "remote-ready" is rather easy: simply add the "--track" flag and the remote branch's ref like in the following example:<br /><br />

```bash
$ git checkout --track origin/dev
Branch dev set up to track remote branch dev from origin.
Switched to a new branch 'dev'
```

Based on the remote branch "origin/dev", we now have a new local branch named "dev".