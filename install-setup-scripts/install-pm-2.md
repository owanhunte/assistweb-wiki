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

Default process name is the filename without .js (eg: app for app.js). Use --name or -n to change. Once in your process list, use the process name to interact with your application.<br><br>


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