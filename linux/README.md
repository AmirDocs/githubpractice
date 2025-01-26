# Linux Guide

This guide covers various tasks related to Linux systems, including Bash scripting for provisioning a web server, working with Nginx, managing Linux commands, and more.

## Table of Contents

## Table of Contents

- [Bash Shell Scripting](#bash-shell-scripting)
  - [Setting up an Nginx Web Server](#setting-up-an-nginx-web-server)
    - [Updating the System](#updating-the-system)
    - [Upgrading Packages](#upgrading-packages)
    - [Installing Nginx](#installing-nginx)
    - [Starting the Nginx Service](#starting-the-nginx-service)
    - [Checking Nginx Status](#checking-nginx-status)
    - [Restarting Nginx](#restarting-nginx)
    - [Enabling Nginx at Boot](#enabling-nginx-at-boot)
  - [Customising the Nginx Webpage](#customizing-the-nginx-webpage)
    - [Backing Up the Default Nginx Page](#backing-up-the-default-nginx-page)
    - [Replacing the Default Nginx Page](#replacing-the-default-nginx-page)
    - [Downloading an Image](#downloading-an-image)
    - [Adding the Image to the Webpage](#adding-the-image-to-the-webpage)
  - [Running the Bash Script](#running-the-bash-script)
- [Linux Commands](#linux-commands)
  - [Common Commands](#common-commands)
  - [Environment Variables](#environment-variables)
  - [Piping and Redirection](#piping-and-redirection)
  - [Managing File Permissions](#managing-file-permissions)

## Bash Shell Scripting

### Setting up an Nginx Web Server

#### Updating the System

To refresh the package list on your system, run the following:

```bash
sudo apt update
```

#### Upgrading Packages

To upgrade all the installed packages to the latest versions:

```bash
sudo apt upgrade -y
```

#### Installing Nginx

![alt text](<Screenshot 2025-01-24 120253.png>)

To install the Nginx web server:

```bash
sudo apt install nginx
```

#### Starting the Nginx Service

To start the Nginx service:

```bash
sudo systemctl start nginx
```

#### Checking Nginx Status

To check the status of Nginx and its process ID (PID):

```bash
sudo systemctl status nginx
```

#### Restarting Nginx

If you make changes to the Nginx configuration files, restart it to apply the changes:

```bash
sudo systemctl restart nginx
```

#### Enabling Nginx at Boot

To ensure Nginx starts automatically when the system boots:

```bash
sudo systemctl enable nginx
```

### Customising the Nginx Webpage

#### Backing Up the Default Nginx Page

The default Nginx webpage is stored in:

```bash
/var/www/html
```

To create a backup of the default webpage:

```bash
sudo cp index.html index.html.bak
```

#### Replacing the Default Nginx Page

You can now replace the `index.html` file with your own HTML content or design.

#### Downloading an Image

You can download an image to the `html` directory using `wget`:

```bash
cd /var/www/html
wget https://example.com/path-to-your-image.jpg
```

#### Adding the Image to the Webpage

To add the image to your webpage, edit the `index.html` file:

```bash
sudo nano /var/www/html/index.html
```

Inside the `<body>` section, add the following HTML code:

```html
<img src="image.jpg" alt="Custom Image" width="500">
```

### Running the Bash Script

To execute your Bash script, first make it executable:

```bash
chmod +x /path/to/your/script.sh
```

Then run the script:

```bash
./script.sh
```

## Linux Commands

### Common Commands

| Command | Description | Example |
| ------- | ----------- | ------- |
| `mv`    | Move or rename files | `mv file.txt newfile.txt`<br>`mv file.txt /home/user/` |
| `file`  | Get the file type | `file example.jpg` |
| `rm`    | Remove files or directories | `rm file.txt`<br>`rm -r foldername` |
| `mkdir` | Create a directory | `mkdir newfolder` |
| `rmdir` | Remove an empty directory | `rmdir emptyfolder` |
| `touch` | Create a new empty file | `touch newfile.txt` |
| `cat`   | Display the contents of a file | `cat file.txt` |
| `nano`  | Open a text file in the nano editor | `nano file.txt` |
| `head`  | Display the first few lines of a file | `head -n 5 file.txt` |
| `tail`  | Show the last few lines of a file | `tail -n 5 file.txt` |
| `grep`  | Search for a pattern in a file | `grep "searchterm" file.txt` |
| `tree`  | View the directory structure | `sudo apt install tree`<br>`tree` |

## Environment Variables

### What are Environment Variables?

Environment variables store dynamic values that influence processes and programs on the system. They contain details like system paths, user information, and more.

### Common Commands:

To view all environment variables:

```bash
printenv
```

To display the value of a specific variable:
```bash
echo $VARIABLE_NAME
```

To set a new environment variable:
```bash
export VARIABLE_NAME=value
```

For persistent variables, add the export command to `.bashrc` or `.bash_profile`.

## Piping and Redirection

### What is Piping?

Piping allows you to take the output of one command and use it as input for another command.

Example:
```bash
ps aux | grep "processname"
```

#### Redirection:
To redirect output to a file, use:
```bash
command > file
```

## Managing File Permissions

### What are File Permissions?

File permissions control who can read, write, or execute a file. Each file or directory has permissions for the owner, group, and others.

#### Changing Permissions:
```bash
chmod 755 file.txt chmod +x script.sh
```

#### Changing Ownership:
```bash
chown user:group file.txt
```