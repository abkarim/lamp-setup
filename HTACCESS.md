# Htaccess
Htaccess stands for Hypertext Access. It is a configuration file. This file is very handy when a user doesn't have access to the server configuration file. Users are allowed to change the name from .htaccess to something else.

## Change or view access file name
file configurations are located here `/etc/apache2/apache2.conf`. 
```
//...
# AccessFileName: The name of the file to look for in each directory
# for additional configuration directives.  See also the AllowOverride
# directive.
#
AccessFileName .htaccess

#
# The following lines prevent .htaccess and .htpasswd files from being
# viewed by Web clients.
#
<FilesMatch "^\.ht">
        Require all denied
</FilesMatch>
//...
```

## How to enable
It is possible that rewrite rule is not enabled by default.  <br />
**1.** Enable Apache mod_rewrite module
```
sudo a2enmod rewrite
```
**2.** Enable overwrite in `/etc/apache2/sites-enabled/000-default.conf`. Find `<Directory /var/www/> //...Some content</Directory>` and set `AllowOverride All`
```
//...
<Directory /var/www/>
//...
AllowOverride All
//...
</Directory>
//...
```
**Now restart**


## How to use
You can use one `.htaccess` file inside a folder and fortunately, there is no limit. Using multiple `.htaccess` files in a project is so handy.
- Create a .htaccess file
- Enable the rewrite engine by writing `RewriteEngine On`
 
### Comment
Comments are started with `#`
_Example_: `# This is a comment`

### RewriteCond
`RewriteCond` allows executing an action with a condition. It is similar to `if` in a programming language. 
_Example_: We want to redirect user to a specific page if requested url is not a file and also not a folder
```
# Turn on rewrite engine
RewriteEngine On
# Is a file?
RewriteCond %{REQUEST_FILENAME} !-f
# Is a folder
RewriteCond %{REQUEST_FILENAME} !-d
# Condition matched
# Redirect to index.php then it will do something with this request
RewriteRule ^(.*)$ /index.php
```

## RewiteRule
`RewriteRule` is used to rewrite requests.
```
//...
# Redirect to index.php
RewriteRule ^(.*)$ /index.php
```
## Common use cases
- Block directory listing
- Redirect users to another location
- Force HTTPS
- And more...


## Example
Redirect any URL to a specific file. In this case, I’m redirecting to index.php. Here, we cannot access a file or folder since we don't use any conditions.
```
RewriteEngine On
# Redirect all request to index.php file
RewriteRule ^(.+)$ index.php
```
## Tips
- When we use a `.htaccess` file in the project root folder to redirect all requests to a specific file (e.g. `api.php`), and there is no condition. Unfortunately at some point we figure out that, we have a folder called `public` and users need to access it for files eg: `image.img`, we can do that by just creating a empty `.htaccess` file with `RewriteEngine On`. _This file will overwrite all of the previous conditions_. **Horray**, now users can access the `public` folder `https://www.example.com/public`.  
