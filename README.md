# PHP enviroment setup using Docker
### Using NGINX, PHP-FPM, MySQl, PHPMyAdmin

## Overview

1. [Install prerequisites](#install-prerequisites)

    Before installing project make sure the following prerequisites have been met.

2. [Clone this repository](#clone-this-repository)

    Clone this repository into your server

3. [Install your web project](#install-your-web-project)

    Clone your web project inside

4. [Configure Nginx and PHP config](#configure-nginx-php-config)

    Configure the Nginx and PHP config files as per your web project
    
5. [Configure Dockerfile and docker-compose.yml](#configure-dockerfile-and-docker-compose.yml)

    Configure the Dockerfile and docker-compose.yml as per your web project

6. [Run your project](#run-your-project)

    Now run the web project using docker commands
    
7. [Generate SSL certificates and setup auto renew](#generate-ssl-certificates-and-setup-auto-renew) [`Optional`]

    Additionally, generate SSL certificates for securing server and setup auto renew

8. [Using docker commands](#using-docker-commands)

    Use these docker commands for recurring operations
    
___

## Install Prerequisites