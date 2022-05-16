INSTALLATION OF SPURT COMMERCE 
-------------------------------------

PREREQUISITES:
--------------

If you want to deploy Spurtcommerce into your server, you need to have the following software installed in your system.

· Node Js Installation (Version — 14.x)

· Apache Installation

· MySQL Installation

· Imagemagick Installation

· Angular Installation


STEP:1 INSTALLING NODEJS 
--------------------------

curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -

sudo apt-get install -y nodejs

sudo apt-get install -y build-essential 

 sudo npm install forever -g

 sudo npm install apidoc -g


 STEP:2 APACHE INSTALLATION
 ------------------------------

sudo apt update

 sudo apt install apache2

sudo a2enmod proxy

sudo a2enmod proxy_http

sudo a2enmod headers

sudo systemctl restart apache2

sudo systemctl status apache2

STEP:3 Mysql Installation
---------------------------

sudo apt install mysql-server

sudo systemctl start mysql.service

 sudo mysql -u root

 SELECT User, Host, plugin FROM mysql.user;

 ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY "P@ssw0rd";

 FLUSH PRIVILEGES;

 Exit;


 STEP:4 Imagemagick Installation
 --------------------------------

 For all the image manipulation in Spurtcommerce, we have used Imagemagick. With the following commands, you can install Imagemagick.

 sudo apt update

sudo apt install imagemagick


STEP:5 Angular Installation
---------------------------------

The Front End of Spurtcommerce Application is built on Angular framework. By using the following command, you can install Angular in your server.

$ sudo npm install -g @angular/cli

Note: We recommend minimum 4gb RAM for installing Angular CLI.


STEP:6 Application Setup
-----------------------

Back End API Setup :
---------------------

Download Community version of Spurt Commerece Zip file to windows 

scp .\Spurtcommerce_3.0.2_community_LTS.zip ubuntu@54.227.189.101:/home/ubuntu/

 sudo unzip Spurtcommerce_3.0.2_community_LTS.zip


cd api

sudo npm install

sudo npm install bcrypt@5.0.1






 



