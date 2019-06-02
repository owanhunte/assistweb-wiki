<!-- TITLE: Using htop To Monitor System Processes on Linux -->

On Linux distributions, the *`top`* command line utility allows us to see what process is consuming the most CPU or memory. There’s a similar utility called *`htop`* (an interactive process viewer for Unix systems) which we recommend over top, as it offers an improved user interface and is much easier to use for normal tasks.

The first great thing about htop is that it will show you your usage per CPU, as well as a meaningful text graph of your memory and swap usage right at the top, as shown in the following screenshot. At a glance, this is much easier to understand than the default output from top.

![Htop Screenshot 1](/uploads/linux/htop-screenshot-1.png "Htop Screenshot 1")
# Installing htop on Ubuntu
htop is not installed by default on most Linux distributions — here’s the command you’ll need to install it on Ubuntu:<br /><br />

```batchfile
sudo apt install htop
```

Once installed, just type `htop` at a terminal to launch it, and notice the great text-mode graph at the top of the display, similar to what is shown in the above screenshot.

To select a process, just use your Up/Down arrow keys, and then you can kill it with the F9 key if you’d like, or you can change the priority by using the F7 and F8 keys. Use the F6 key to easily change the default sort column, as shown below:

![Htop Screenshot 2](/uploads/linux/htop-screenshot-2.png "Htop Screenshot 2")