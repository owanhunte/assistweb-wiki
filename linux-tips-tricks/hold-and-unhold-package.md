<!-- TITLE: How to Hold or Unhold an Installed Software Package -->

On Linux Debian-based distros such as Ubuntu, apt/apt-get will typically upgrade the packages when a newer version becomes available. To prevent unintended upgrades, you can pin the package at the currently installed version. For example, to pin the currently installed MongoDB package you can use the following commands:<br /><br />

```bash
echo "mongodb-org hold" | sudo dpkg --set-selections
echo "mongodb-org-server hold" | sudo dpkg --set-selections
echo "mongodb-org-shell hold" | sudo dpkg --set-selections
echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
echo "mongodb-org-tools hold" | sudo dpkg --set-selections
```
<br />

To remove the hold on a package use the following command:<br /><br />

```bash
sudo apt-mark unhold package_name
```
<br />

If the removal was successful you should get the message ***Canceled hold on packagename***.