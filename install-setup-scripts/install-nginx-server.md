<!-- TITLE: Install NGINX Server -->
<!-- SUBTITLE: ...on Linux Ubuntu Server 18.04 LTS -->

# Installing from the default Ubuntu Repository
**Note:** This is the quickest way, but generally the provided package is outdated. Update the Ubuntu repository information and install the package using the following commands:<br><br>

```batchfile
$ sudo apt update && sudo apt upgrade -y
$ sudo apt install nginx -y
```
<br>

Run the following commands to start and check the status of NGINX:<br><br>

```batchfile
$ sudo systemctl status nginx    # To check the status of nginx
$ sudo systemctl start nginx     # To start nginx
```
<br>

Ensure every time you restart your system NGINX starts up automatically:<br><br>

```batchfile
$ sudo systemctl enable nginx
```
<br>

To verify the installation and check the version:<br><br>

```batchfile
$ sudo nginx -v
nginx version: nginx/1.14.0 (Ubuntu)
```
<br>

# Installing from the Official NGINX Repository
Download the key used to sign NGINX packages and the repository, and add it to the `apt` program’s key ring:<br><br>

```batchfile
$ sudo wget https://nginx.org/keys/nginx_signing.key
$ sudo apt-key add nginx_signing.key
```
<br>

Edit the **/etc/apt/sources.list** file, for example with **`vi`**:<br><br>

```batchfile
$ sudo vi /etc/apt/sources.list
```
<br>

Add these lines to **sources.list** to name the repositories from which the NGINX open source source can be obtained:<br><br>

```batchfile
deb https://nginx.org/packages/mainline/ubuntu/ <CODENAME> nginx
deb-src https://nginx.org/packages/mainline/ubuntu/ <CODENAME> nginx
```
<br>

where:

* The **`/mainline`** element in the pathname points to the latest mainline version of NGINX open source; delete it to get the latest stable version
* **`<CODENAME>`** is the codename of an Ubuntu release.

For example, to get the latest stable package for Ubuntu 18.04 (“bionic”), add:<br><br>

```batchfile
deb https://nginx.org/packages/ubuntu/ bionic nginx
deb-src https://nginx.org/packages/ubuntu/ bionic nginx
```
<br>

Save the changes and quit **`vi`** (press ESC and type **`wq`** at the `**:**` prompt).

Install NGINX open source:<br><br>

```batchfile
$ sudo apt remove nginx-common
$ sudo apt update
$ sudo apt install nginx
```
<br>

Run the following commands to start and check the status of NGINX:<br><br>

```batchfile
$ sudo systemctl status nginx    # To check the status of nginx
$ sudo systemctl start nginx     # To start nginx
```
<br>

Ensure every time you restart your system NGINX starts up automatically:<br><br>

```batchfile
$ sudo systemctl enable nginx
```
<br>


Verify that NGINX open source is up and running:<br><br>

```batchfile
$ curl -I 127.0.0.1
HTTP/1.1 200 OK
Server: nginx/1.16.0
...
```
<br>

# Configuring the websites
The configuration files for each website you want to setup on NGINX should be placed in the <code>/etc/nginx/conf.d</code> path, with a `.conf` extension. The following is a sample (non-SSL enabled) configuration file for the *AssistWeb website*, which is currently a NodeJS application.<br><br>

```batchfile
upstream nodejs {
    # List of Node.JS Application Servers (only 1 for now)
    server 172.31.24.46:8081;
}

server {
    listen 80;
    listen [::]:80;
    server_name  www.assistweb.co;
    return 301 http://assistweb.co$request_uri;
}

server {
    listen 80;
    listen [::]:80;

    server_name assistweb.co;

    location / {
        proxy_pass http://nodejs;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
```
<br>

To test configuration changes to the site configuration files and reload NGINX, run the following commands:<br><br>

```batchfile
sudo nginx -t
sudo /etc/init.d/nginx reload
```
<br>