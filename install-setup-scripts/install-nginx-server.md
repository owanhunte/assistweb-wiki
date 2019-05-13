<!-- TITLE: Install Nginx Server -->
<!-- SUBTITLE: ...on Linux Ubuntu Server 18.04 LTS -->

First, install the latest version of Nginx server using the following commands:<br><br>

```bash
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install nginx -y
```
<br>

Run the following commands to start and check the status of Nginx:<br><br>

```bash
sudo systemctl status nginx    # To check the status of nginx
sudo systemctl start nginx     # To start nginx
```
<br>

Ensure every time you restart your system Nginx starts up automatically:<br><br>

```bash
sudo systemctl enable nginx
```

# Configure the websites
The configuration files for each website you want to setup on Nginx are found in the <code>/etc/nginx/sites-available</code> path. Initially there is just the **default** file which should of course be modified as needed.