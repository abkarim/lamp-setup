# PHP with apache web server
We have to setup PHP for using with apache web server. We will install php8.1 in our system.

## Download
[download file](https://www.php.net/downloads.php) -tar.gz. 

## Install
### Option 1
Open terminal and enter this command
####
```
sudo apt install php8.1
```

### Option 2
Open download folder and extract package
```
tar -xzvf php-{version}.tar.gz
```

Enter this command to download all prerequisite
```
sudo apt install pkg-config libxml2-dev libsqlite3-dev php-mysql
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

## Configure apache to use PHP
This option will use the latest stable PHP version
```
sudo apt install libapache2-mod-php
```

## Error reporting
To show error you need to set `display_errors = On` in `/etc/php/{version}/apache2/php.ini`. **Don't enable in production**
```
//...
display_errors = On
//...
```

**Restart apache**
