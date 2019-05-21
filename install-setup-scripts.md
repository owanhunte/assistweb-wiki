<!-- TITLE: Install/Setup Scripts -->
<!-- SUBTITLE: A reference collection of Linux-specific install/setup scripts -->

# Ubuntu Production Server Setup
At AssistWeb, Ubuntu is our Linux server OS of choice. The install script we use for setting up Ubuntu 18.04 LTS production servers immediately after provisioning can be found here:

* https://gist.github.com/owanhunte/0e158d10963e015f7f0ae2ec17e7f5a7

# Apache2/PHP Install Scripts for Ubuntu/Debian/Mint
We've created a [**GitHubGist**](https://gist.github.com/owanhunte/9c56ef421c333911fb4497914cba8a53) containing a collection of scripts that allow Apache 2.4, PHP 5.6, PHP 7.1 and PHP 7.2 to be installed on Ubuntu 18.04 LTS or higher. These scripts would also work for the latest version of Debian and Mint.

*   _install_apache_php.sh_ - Installs the latest version of Apache (currently 2.4) as well as PHP versions 5.6, 7.1 and 7.2.
*   _install_php_modules.sh_ - Installs a set of PHP modules necessary for the running of the vast majority of PHP-based websites.
*   _useful_commands.sh_ - Useful commands that allow you to do things such as check the status of the Apache and PHP services and restart the services.
*   _setup_ssl.sh_ - Provides instructions for installing packages to install and renew SSL certificates for your Apache websites.
*   _php_ini_settings.md_ - Provides suggestions for recommended PHP configuration settings after running _install_apache_php.sh_ and _install_php_modules.sh_

The gist can be found here: https://gist.github.com/owanhunte/9c56ef421c333911fb4497914cba8a53

# Installing NGINX on Ubuntu Server 18.04
[How to install, setup and configure Nginx HTTP server](/install-setup-scripts/install-nginx-server)

# Installing PM2
[PM2 Runtime](/install-setup-scripts/install-pm-2)