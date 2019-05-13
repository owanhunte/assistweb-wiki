<!-- TITLE: Install NGINX Server -->
<!-- SUBTITLE: ...on Linux Ubuntu Server 18.04 LTS -->

# Installing from the default Ubuntu Repository
Install the latest version of NGINX server using the following commands:<br><br>

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install nginx -y
```
<br>

Run the following commands to start and check the status of NGINX:<br><br>

```bash
sudo systemctl status nginx    # To check the status of nginx
sudo systemctl start nginx     # To start nginx
```
<br>

Ensure every time you restart your system NGINX starts up automatically:<br><br>

```bash
sudo systemctl enable nginx
```
<br>

To verify the installation and check the version:<br><br>

```bash
$ sudo nginx -v
nginx version: nginx/1.14.0 (Ubuntu)
```
<br>

# Configuring the websites
The configuration files for each website you want to setup on NGINX are found in the <code>/etc/nginx/sites-available</code> path. Initially there is just the **default** file which should of course be modified as needed.

To test configuration changes to the site configuration files and reload NGINX, run the following commands:<br><br>

```bash
sudo nginx -t
sudo /etc/init.d/nginx reload
```
<br>