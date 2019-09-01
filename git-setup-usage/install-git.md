<!-- TITLE: Install Git -->
<!-- SUBTITLE: Download links and commands for installing Git -->

Download links and instructions can be found at the following site: [https://git-scm.com/downloads](https://git-scm.com/downloads)
# Download for Debian/Ubuntu Linux distros
For the latest stable version for your release of Debian/Ubuntu:<br /><br />

```bash
apt-get install git
```

For Ubuntu, this PPA provides the latest stable upstream Git version:<br /><br />

```bash
 add-apt-repository ppa:git-core/ppa
 apt update
 apt install git
```

If you run into any errors running these commands try using `sudo` at the beginning of each. This will of course only work if you are running these commands from an administrator account.