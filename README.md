# Source-codes

## Lampstack extras
# Enable PHP website
* <img width="724" alt="extra1" src="https://github.com/Gailpositive/Source-codes/assets/111061512/4d192a48-950d-49d7-9066-1e966bfe55bd">
* There is a CODE BELOW, CLICK EDIT
* <IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>

* Relaod apache2 with the command: $ sudo systemctl reload apache2
* <img width="647" alt="extra 2" src="https://github.com/Gailpositive/Source-codes/assets/111061512/0087b6af-e01d-46ce-8eb0-a8d63b694b9a">
*Next, vi the file with the command "$ vim /var/www/projectlamp/index.php"
* Write this code in the vi "
  <?php
phpinfo();
 * As seen in this image below
 * <img width="702" alt="extra3" src="https://github.com/Gailpositive/Source-codes/assets/111061512/eba2c6d1-7a50-46fb-b203-9604ba966399">

 *  <img width="779" alt="extra 4" src="https://github.com/Gailpositive/Source-codes/assets/111061512/019735b1-2805-4a39-91f2-7431ae712bf7">
* $ sudo rm /var/www/projectlamp/index.php




## 

* <img width="765" alt="extra 1" src="https://github.com/Gailpositive/Source-codes/assets/111061512/56b815ff-d92d-483d-9cdb-5926e0e1ed5c">

* <img width="747" alt="extra 2 PNG" src="https://github.com/Gailpositive/Source-codes/assets/111061512/d620ba02-f1c9-4cf0-94f6-1403750fa8c2">

* click on edit to see code below
*  #/etc/nginx/sites-available/projectLEMP

server {
    listen 80;
    server_name projectLEMP www.projectLEMP;
    root /var/www/projectLEMP;

    index index.html index.htm index.php;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php8.1-fpm.sock;
     }

    location ~ /\.ht {
        deny all;
    }

}


* <img width="765" alt="extra 1" src="https://github.com/Gailpositive/Source-codes/assets/111061512/56b815ff-d92d-483d-9cdb-5926e0e1ed5c">

* <img width="747" alt="extra 2 PNG" src="https://github.com/Gailpositive/Source-codes/assets/111061512/d620ba02-f1c9-4cf0-94f6-1403750fa8c2">

* <img width="688" alt="extra 3" src="https://github.com/Gailpositive/Source-codes/assets/111061512/c7372920-4ca3-4c8c-b510-dc3e2031a6dd">

* <img width="691" alt="extra 4" src="https://github.com/Gailpositive/Source-codes/assets/111061512/10eb4455-189e-43e3-aee5-d8c676b8032c">

* $ sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/

* <img width="709" alt="extra 5" src="https://github.com/Gailpositive/Source-codes/assets/111061512/29ceded2-e23e-48f4-a84b-39c9efaa7115">

* <img width="786" alt="extra 6" src="https://github.com/Gailpositive/Source-codes/assets/111061512/0169e93f-e29c-47e9-8a96-770796fc2689">

* sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html


* <img width="828" alt="extra 7" src="https://github.com/Gailpositive/Source-codes/assets/111061512/01ddc7a5-3b11-42d1-81ea-400b5fbaae06">

* <img width="745" alt="extra 8" src="https://github.com/Gailpositive/Source-codes/assets/111061512/8b24fab2-0956-4ea6-b02b-9e7cff45dc3a">






