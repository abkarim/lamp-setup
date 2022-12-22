# PHP with apache web server
We have to setup PHP for using with apache web server. We will install php-8.2.0 in our system.

## Download
[download file](https://www.php.net/downloads.php) -tar.gz. 

## Install
Open download folder and extract package
```
tar -xzvf php-{version}.tar.gz
```

Enter this command to download all prerequisite
```
sudo apt install pkg-config libxml2-dev libsqlite3-dev
```

Open `php-{version}` folder and enter this command to configure php build
```
./configure
```

Compile and install php
```
make
```
```
sudo make install
```

Configure apache to use PHP
```
sudo apt install libapache2-mod-php
```
**Restart apache**
