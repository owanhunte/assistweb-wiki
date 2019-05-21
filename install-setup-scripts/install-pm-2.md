<!-- TITLE: Install PM2 Runtime -->
<!-- SUBTITLE: Production Process Manager for Node.js applications -->

PM2 Runtime is a Production Process Manager for Node.js applications with a built-in Load Balancer. It allows us to keep our applications alive forever, to reload them without downtime and facilitate common Devops tasks.
# Install pm2
With npm:<br><br>

```batchfile
npm install pm2 -g
```
<br>

# CLI autocompletion
By default, CLI autocompletion is not installed with PM2, so run the command `pm2 completion install` to install it.

# Updating
Keep pm2 up to date with `npm install pm2 -g && pm2 update`.

# The process list
The process list is where all running applications are registered. Manage your process list in a few commands:<br><br>

```batchfile
# start and add a process to your list
pm2 start app.js

# show your list
pm2 ls

# stop and delete a process from the list
pm2 delete app
```
<br>

The default process name is the filename without .js (eg: app for app.js). Use --name or -n to change. Once in your process list, use the process name to interact with your application.<br><br>

```batchfile
# stop the process (kill the process but keep it in the process list)
pm2 stop app

# start the process
pm2 start app

# both stop and start
pm2 restart app
```
<br>

# Access your logs
Access your logs in realtime with `pm2 logs app`.

Consult your logs history files in the `~/.pm2/logs` folder.

# Startup Hook
The purpose of a startup hook is to save your process list and bring it back at machine restarts, even unexpected ones.

Each OS has a specific tool to handle startup hooks: PM2 provides an easy way to generate and configure them. To detect available init systems on your machine and generate a configuration, run `pm2 startup`. Running that command on one of our Ubuntu EC2 instances for example resulted in the following output:<br><br>

```batchfile
pm2 startup
$ [PM2] Init System found: systemd
$ [PM2] To setup the Startup Script, copy/paste the following command:
$ sudo env PATH=$PATH:/home/ubuntu/.nvm/versions/node/v10.15.3/bin /home/ubuntu/.nvm/versions/node/v10.15.3/lib/node_modules/pm2/bin/pm2 startup systemd -u ubuntu --hp /home/ubuntu
```
<br>

Copy and paste in the CLI the ouput of this command to set up your startup hook.

> **Note**: With NVM, the `pm2` path change when updating Node.js. You need to run the `startup` command after every update.

<br><br>
## Disabling Startup System

```batchfile
pm2 unstartup
```
<br>

## Update startup hook

To update the startup hook run the following commands:<br><br>

```batchfile
pm2 unstartup
pm2 startup
```
<br>