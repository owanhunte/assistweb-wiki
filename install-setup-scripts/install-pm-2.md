<!-- TITLE: Install PM2 Runtime -->
<!-- SUBTITLE: Production Process Manager for Node.js applications -->

PM2 Runtime is a Production Process Manager for Node.js applications with a built-in Load Balancer. It allows us to keep our applications alive forever, to reload them without downtime and facilitate common Devops tasks.

# Install pm2
With npm:<br><br>

```bash
npm install pm2 -g
```
<br>

# CLI autocompletion
By default, CLI autocompletion is not installed with PM2, so run the following command to install it:<br><br>

```bash
pm2 completion install
```
<br>

# Updating
Keep pm2 up to date with:<br><br>

```bash
npm install pm2 -g && pm2 update
```
<br>

# The process list
The process list is where all running applications are registered. Manage your process list in a few commands:<br><br>

```bash
# start and add a process to your list
pm2 start app.js

# show your list
pm2 ls

# stop and delete a process from the list
pm2 delete app
```
<br>
