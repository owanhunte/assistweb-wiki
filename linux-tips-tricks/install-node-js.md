<!-- TITLE: Install Node.js -->
<!-- SUBTITLE: ...on Linux Ubuntu 18.04 LTS using Node Version Manager (NVM) -->

# Install cURL
Install cURL if it is not yet present on the system, via the terminal:<br><br>

```bash
sudo apt install curl
```
<br>

# Install nvm
Install nvm via cURL:<br><br>

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.0/install.sh | bash
```
<br>

# Install Node via nvm
To download, compile and install the latest release of node, use this command:<br><br>

```bash
nvm install node # "node" is an alias for the latest version
```
<br>

To install a specific version of node:<br><br>

```bash
nvm install 10.16.3
```
<br>

The first version installed becomes the default. New shells will start with the default version of node (e.g., ```nvm alias default```).

You can list available versions using ls-remote:<br><br>

```bash
nvm ls-remote
```
<br>

To set a specific version as the default version use the command:<br><br>

```bash
nvm use node # sets the latest release as the default version
nvm use 10.16.3 # sets v10.16.3 as the default version
```
<br>

To upgrade to the latest working `npm` on the current, default node version use the command:<br><br>

```bash
nvm install-latest-npm
```
<br>