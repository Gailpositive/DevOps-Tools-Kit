## Check the root below to change it




server {

    listen 80;

    index index.html index.php index.py;


    server_name _;

 

    location / {

 

    try_files $uri $uri/ =404;    

    }

}





server {
    listen 90;
    index index.html index.php index.py;

    server_name _;

 

    root /var/www/darey.io;

 

    location / {

 

    try_files $uri $uri/ =404;    
    }
}
