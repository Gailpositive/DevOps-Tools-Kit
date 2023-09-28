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


