INSTALLTION OF NOP COMMERCE
---------------------------------

STEP:1 CREATING ANSIBLE MASTER AND NODE 1
-----------------------------------

ANSIBLE MASTER :
----------------

sudo apt update

sudo apt upgrade

sudo apt install ansible

ansible --version


STEP 2: ADD SUDO USER 
--------------------

sudo adduser devops

Give Paswword

Login and check the new user

Now again loginto the root with :

sudo -i

STEP 3: ADDING USER TO THE SUDOERS GROUP AND CHNAGING PASSWORD AUTHENTICATION:
-------------------------------------------------------------

sudo vi /etc/ssh/sshd_config

change password authentication to Yes

sudo systemctl restart sshd

sudo visudo 

add devops user to sudoers group

devops  ALL=(ALL:ALL) ALL


STEP 3:CRAETE DIRECTORY AND HOST FILE ON DEVOPS USER HOME
-----------------------------------------------------------

login to devops user: su devops

mkdir myjobs

cd myjobs 

touch hosts


step 4: change the defualt inventory to my home inventory
----------------------------------------------------------

sudo vi /etc/ansible/ansible.cfg

inventory = /home/devops/myjobs/hosts/

STEP 5: LOGIN TO THE NODE SERVER AND CREATE SAME USER CREDENTIALS
-----------------------------------------------------------------

sudo adduser devops

sudo vi /etc/ssh/ssd_config

sudo systemctl restart sshd

password authentication : yes

sudo visudo 

devops ALL=(ALL:ALL) ALL


STEP:6 CREATING SSH KEYGEN AND ADD TO THE NODES
-------------------------------------------------

ssh-keygen

ssh-copy-id  <node1 IP address>

now try login without password to node

ssh <node 1 ip address>

STEP:7 CHECK HOSTS ARE PINGLING 
-----------------------------------

vi hosts

add IP address of Nodes

ansible all -m ping 

STPE:8