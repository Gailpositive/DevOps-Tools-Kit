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




## Lemp stack Implementation

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


## Retrieving data from mysql data base with php
* <img width="791" alt="extra 9" src="https://github.com/Gailpositive/Source-codes/assets/111061512/bb55eb60-1c85-404b-85bb-e6141e8ca3a3">

 * <img width="791" alt="extra 10" src="https://github.com/Gailpositive/Source-codes/assets/111061512/a1282acc-3e31-4f19-9117-2c4b3e8033c3">

* mysql>  CREATE USER 'example_user'@'%' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';

* <img width="837" alt="extra 11" src="https://github.com/Gailpositive/Source-codes/assets/111061512/d0c0a7e5-f2fa-42d9-b7f0-056a7039b2b6">

* mysql> GRANT ALL ON example_database.* TO 'example_user'@'%';

* <img width="780" alt="extra 12" src="https://github.com/Gailpositive/Source-codes/assets/111061512/883bfe40-2244-4b62-ae4a-742dd7d3af9a">

* <img width="914" alt="extra 13" src="https://github.com/Gailpositive/Source-codes/assets/111061512/b86cd60b-0320-4c21-ab0c-7a7095055b83">


* CREATE TABLE example_database.todo_list (item_id INT AUTO_INCREMENT,content VARCHAR(255),PRIMARY KEY(item_id));

* <img width="930" alt="extra 14" src="https://github.com/Gailpositive/Source-codes/assets/111061512/f369ca55-615c-418e-a83b-b6d21421e364">

* <img width="911" alt="extra 15" src="https://github.com/Gailpositive/Source-codes/assets/111061512/97435480-fa56-46a1-be13-64d2c04e9492">

* <img width="880" alt="extra 16" src="https://github.com/Gailpositive/Source-codes/assets/111061512/171d6048-d4e1-47ce-8889-daf69fe98610">

* Edit to see code block
*  <?php
$user = "example_user";
$password = "PassWord.1";
$database = "example_database";
$table = "todo_list";

try {
  $db = new PDO("mysql:host=localhost;dbname=$database", $user, $password);
  echo "<h2>TODO</h2><ol>";
  foreach($db->query("SELECT content FROM $table") as $row) {
    echo "<li>" . $row['content'] . "</li>";
  }
  echo "</ol>";
} catch (PDOException $e) {
    print "Error!: " . $e->getMessage() . "<br/>";
    die();
}

* <img width="797" alt="extra 17" src="https://github.com/Gailpositive/Source-codes/assets/111061512/26c2afc0-bda3-429d-8212-7e60234e3a86">


## Shell Scripting

* <img width="753" alt="extra 1" src="https://github.com/Gailpositive/Source-codes/assets/111061512/f7b7b50d-2cf2-49c3-b42f-b622b00b8e47">

* <img width="830" alt="extra 2" src="https://github.com/Gailpositive/Source-codes/assets/111061512/d7e650bd-ba37-48e0-962a-83188b2ef8b5">

* Edit to view code block
* 
* #!/bin/bash

# Example script to check if a number is positive, negative, or zero

read -p "Enter a number: " num

if [ $num -gt 0 ]; then
    echo "The number is positive."
elif [ $num -lt 0 ]; then
    echo "The number is negative."
else
    echo "The number is zero."
fi


* <img width="928" alt="extra 3" src="https://github.com/Gailpositive/Source-codes/assets/111061512/731b327d-06d0-4a62-b28a-eefd3c18b579">

* Edit to see code block
* #!/bin/bash

# Example script to print numbers from 1 to 5 using a for loop

for (( i=1; i<=5; i++ ))
do
    echo $i
done


* <img width="870" alt="extra 4" src="https://github.com/Gailpositive/Source-codes/assets/111061512/5ba15ba9-43aa-46c0-8b7a-1243f763d3cf">

* <img width="932" alt="extra 5" src="https://github.com/Gailpositive/Source-codes/assets/111061512/dad54e06-d7eb-422f-8c55-ac4727f506fa">

* <img width="952" alt="extra 6" src="https://github.com/Gailpositive/Source-codes/assets/111061512/9b0ab433-9b59-4213-9244-f30be62d20c2">

* <img width="901" alt="extra 7" src="https://github.com/Gailpositive/Source-codes/assets/111061512/598ce476-f95c-4b8d-a266-5be697eff88c">

* #!/bin/bash

# Define a function to greet the user
greet() {
    echo "Hello, $1! Nice to meet you."
}

# Call the greet function and pass the name as an argument
greet "John"
