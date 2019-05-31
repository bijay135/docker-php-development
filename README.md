# PHP enviroment setup using Docker
### Using NGINX, PHP-FPM, MySQl, PHPMyAdmin

## Overview

1. [Install prerequisites](#install-prerequisites)

    Before installing project make sure the following prerequisites have been met.

2. [Clone this repository](#clone-this-repository)

    Clone this repository into your server

3. [Install your web project](#install-your-web-project)

    Clone your web project inside

4. [Configure Nginx and PHP config](#configure-nginx-and-php-config)

    Configure the Nginx and PHP config files as per your web project
    
5. [Configure Dockerfile and docker-compose.yml](#configure-dockerfile-and-docker-composeyml)

    Configure the Dockerfile and docker-compose.yml as per your web project

6. [Run your project](#run-your-project)

    Now run the web project using docker commands
    
7. [Generate SSL certificates and setup auto renew](#generate-ssl-certificates-and-setup-auto-renew) [`Optional`]

    Additionally, generate SSL certificates for securing server and setup auto renew

8. [Using docker commands](#using-docker-commands)

    Use these docker commands for recurring operations
___

## Install Prerequisites

These are the required requisties for buildling a PHP enviroment :

* [Git](https://git-scm.com/downloads)

Check if `Git` is installed using the command :

```sh
git --version
```

___

* [Docker](https://docs.docker.com/engine/installation/)

Install `Docker` easily by using this script :

```sh
curl -sSL https://get.docker.com/ | sh
```

Enable `Docker` at startup

```sh
systemctl docker enable
```

Verify `Docker` version :

```sh
docker --version
```

___

* [Docker Compose](https://docs.docker.com/compose/install/)

Install `Docker Compose` using this script :

```sh
sudo curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

Set file permissions :

```sh
sudo chmod +x /usr/local/bin/docker-compose
```

Verify `Docker Compose` version :

```sh
docker-compose --version
```

___

* [Certbot](https://certbot.eff.org/) [`Optional`]

Add the `Certbot` repository :

```sh
sudo add-apt-repository ppa:certbot/certbot
```

Update the package list :

```sh
sudo apt-get update
```

Finally, install `Certbot` package :

```sh
sudo apt-get install certbot
```

___

### Docker Image to use

* [Nginx](https://hub.docker.com/_/nginx/)
* [PHP-FPM](https://hub.docker.com/r/nanoninja/php-fpm/)
* [MySQL](https://hub.docker.com/_/mysql/)
* [PHPMyAdmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin/)


This project uses the following ports :

| Server     | Port |
|------------|------|
| Nginx      | 80   |
| Nginx SSL  | 443  |
| MySql      | 3306 |
| PHPMyAdmin | 8000 |

___

## Clone this repository

Git clone this repository into your server :

```sh
git clone https://sakwo.sastodeal.com/bijay135/php-ci-cd
```

Go to the project directory :

```sh
cd php-ci-cd
```

### Repository Tree Structure

![Project Tree](doc/project-tree.png)

___

## Install your web project

After moving inside the repository root directory. Move inside `www` folder :

```sh
cd www
```

Now `Git` clone your web project inside it :

```sh
git clone https://your_project_link
```

Now your project has been installed into this repository sccessfully

___

## Configure Nginx and PHP config

Open the Nginx config using `Vim` editor :

```sh
sudo vi server/nginx/default.conf
```

```sh
# Nginx configuration

server {
	listen 80;
	server_name host_name.com www.host_name.com;
	
	root /var/www/html/web_root;
	index index.php;
    
	location / {
		try_files $uri $uri/ /index.php;
	}
	
	location ~ \.php$ {
		fastcgi_pass php:9000;
		include fastcgi_params;
		fastcgi_index index.php;
		fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
	}
}
```

Replace the `host_name.com` with your domain name and `web_root` with top level directory of your web project in all occurrences.

Save the config file by pressing `escape` inside vim editor and typing the following :

```sh
:wq
```

Hit `enter` to save and quit the editor

___

Open the PHP config using Vim editor :

```sh
sudo vi server/php/php.ini
```

```sh
# PHP configuration

```

Add your required PHP `configuration` and press `escape` and type following to save and exit :

```sh
:wq
```

___

## Configure Dockerfile and docker-compose.yml









