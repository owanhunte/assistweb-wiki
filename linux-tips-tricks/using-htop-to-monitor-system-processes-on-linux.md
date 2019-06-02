<!-- TITLE: Using htop To Monitor System Processes on Linux -->

On Linux distributions, the *top* command line utility allows us to see what process is consuming the most CPU or memory. There’s a similar utility called *htop* which we recommend over top, as it offers an improved user interface and is much easier to use for normal tasks.

The first great thing about htop is that it will show you your usage per CPU, as well as a meaningful text graph of your memory and swap usage right at the top, as shown in the following screenshot. At a glance, this is much easier to understand than the default output from top.

![Htop Screenshot 1](/uploads/linux/htop-screenshot-1.png "Htop Screenshot 1")
# Installing htop on Ubuntu
htop is not installed by default on most Linux distributions — here’s the command you’ll need to install it on Ubuntu:<br /><br />

```batchfile
sudo apt install htop
```

Once installed, just type `htop` at a terminal to launch it, and notice the great text-mode graph at the top of the display, similar to what is shown in the above screenshot.