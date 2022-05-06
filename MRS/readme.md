INSTALLATION OF OPENMRS
------------------------------

STEP:1 INSTALL UBUNTU UPDATES
------------------------------

sudo apt update

STEP:2 INSTALL WEB BROWSERS
---------------------------
sudo apt install firefox

Step:3 INSTALLATION OF JAVA OPENJDK-11-JDK
-------------------------------------------

sudo apt-get install openjdk-11-jdk

STEP:4 TOMCAT9 SETUP
----------------------

sudo useradd tomcat9

cd /opt

sudo apt install tomcat9

sudo apt install tomcat9-admin

Test tomcat Ports :
----------------------

ss -ltn


Permission :
--------------
sudo chown tomcat9.tomcat9 apache-tomcat9

sudo ufw allow from any to any port 8080 proto tcp


 sudo nano /etc/tomcat9/tomcat-users.xml

 Copy :
 -------

 <role rolename="tomcat"/>                                                    
<role rolename="admin"/>                                                     
<role rolename="manager"/>                                                   
<role rolename="manager-gui"/>
<user name="admin" password="XXXXXX" roles="tomcat,admin,manager,manager-gui"/>


STEP 5:  CREATE OPENMRS DIRECTORY
---------------------------------------

sudo mkdir /usr/share/tomcat9/.OpenMRS

sudo chown -R tomcat9:tomcat9 /usr/share/tomcat9/.OpenMRS/


STEP 6: START THE TOMCAT 9
-----------------------------

sudo service tomcat9 start
sudo service tomcat9 stop
sudo service tomcat9 restart

sudo chown -R tomcat9 /var/lib/tomcat9


STEP 7: INSTALLING MYSQL
-------------------------------

sudo apt-get install mysql-server

set root password:
------------------

sudo mysql -u root

mysql> use mysql;

 ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'P@ssw0rd';

FLUSH PRIVILEGES;

 exit

 step 8: VERIFY THE MYSQL LOGIN WITH root
 -------------------------------------------

 mysql -h localhost -P 3306 --protocol tcp -u root -p

Password:  P@ssw0rd

exit


STEP :9 DEPLOY OPENMRS WAR FILE:
-----------------------------------

sudo apt-get install unzip

wget https://sourceforge.net/projects/openmrs/files/releases/OpenMRS_Platform_2.1.2/openmrs-standalone-2.1.2.zip/download



sudo unzip openmrs-standalone-2.1.2


STEP 10: UNZIP WAR FILE AT TOMCAT /WEBAPP LOCATION
--------------------------------------------------

sudo unzip openmrs.war -d /var/lib/tomcat9/webapps/openmrs

RESTART TOMCAT9
-------------------

sudo service tomcat9 restart


STEP11 : GOTO THE WEB PAGE

 http://localhost:8080/manager/html
 
 http://localhost:8080/openmrs










