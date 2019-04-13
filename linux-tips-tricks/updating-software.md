<!-- TITLE: Updating Software -->
<!-- SUBTITLE: ...on Linux Ubuntu 18.04 LTS -->

# Re-synchronize package index files
**apt update** downloads the package lists from the repositories and "updates" them to get information on the newest versions of packages and their dependencies. It will do this for all repositories and PPAs. In other words it doesn't actually install new versions of software. Instead, it updates the package lists for upgrades for packages that need upgrading, as well as new packages that have just come to the repositories. An update should always be performed before an upgrade or dist-upgrade.<br><br>

```bash
sudo apt update
```
<br>

# Install package upgrades
**apt upgrade** will fetch new versions of packages existing on the machine if APT knows about these new versions by way of apt update. New versions of currently installed packages that cannot be upgraded without changing the install status of another package will be left at their current version.<br><br>

```bash
sudo apt upgrade
```
<br>

# Intelligently handle package dependencies
**apt dist-upgrade** will do the same job which is done by apt upgrade, plus it will also intelligently handle the dependencies, so it might remove obsolete packages or add new ones.<br><br>

```bash
sudo apt dist-upgrade
```