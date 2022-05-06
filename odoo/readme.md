Installing Odoo Community Version
---------------------------------

step 1: update Ubuntu Package
------------------------------
sudo apt update

step 2:install postgre sql
--------------------------
 sudo apt install postgresql -y

#Enable Postgre SQL

 sudo systemctl enable postgresql

#start Postgre SQL

tep 3: Make sure Python3 and PIP installed
--------------------------------------------

Sudo apt install Python3
sudo apt install python3-pip

Step 4: Clone the Odoo 
-------------------------------------
 git clone https://github.com/odoo/odoo.git

 Step 5: Installing Postgre Client
 -----------------------------------
  sudo apt install postgresql postgresql-client

  #adding User:

  sudo -u postgres createuser -s $USER

  createdb $USER

  Step 6 : Install Dependencies for Ubuntu
  -----------------------------------------

  sudo apt install python3-dev libxml2-dev libxslt1-dev libldap2-dev libsasl2-dev \
    libtiff5-dev libjpeg8-dev libopenjp2-7-dev zlib1g-dev libfreetype6-dev \
    liblcms2-dev libwebp-dev libharfbuzz-dev libfribidi-dev libxcb1-dev libpq-dev


STEP:7 Odoo installation
-----------------------
cd odoo

 pip3 install setuptools wheel

  pip3 install -r requirements.txt


Step 8: Installation of Nodejs and Npm
----------------------------------------

sudo curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

sudo apt install nodejs

sudo npm install -g rtlcss

node --version

npm --version


Step 9 : odoo running
--------------------------------

cd /odoo/

python3 odoo-bin --addons-path=addons -d mydb

mydb is the default database to serve on localhost:8069.


check odoo status : ./odoo-bin

Odoo Configurations for Postgre SQL;
----------------------------------

conn = psycopg2.connect("dbname=test user=postgres password=secret")