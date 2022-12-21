# PHP with apache web server
We need to setup PHP for using with apache web server.

## Install
we will install php-8.2 in our system

### Debian
Pre-requisites to installing PHP.

```
sudo apt install apt-transport-https lsb-release ca-certificates wget -y
```

Add GPG key and Sury repository 
```
sudo wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg 
```
```
sudo sh -c 'echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list'
```

Update package repository
```
sudo apt update
```

Install php
```
sudo apt install php8.2
```

Add apache support 
```
sudo apt install php8.2 libapache2-mod-php8.2
```
