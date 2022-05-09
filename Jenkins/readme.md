INSTALLTION OF JENKINS ON UBUNTU 20.04
---------------------------------------------

step 1: Long term Release keyring for Jenkins
-----------------------------------------------

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null

  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null


  step:2 Installing Jenkins
  ------------------------------

  sudo apt-get update
  sudo apt install openjdk-11-jdk

  java --version

  sudo apt-get install jenkins

  jenkins --version

  Step:3 Start Jenkins services
  -----------------------------

  sudo systemctl daemon-reload

   systemctl enable jenkins service

   sudo systemctl start jenkins

   sudo systemctl status jenkins

Step 4: jenkins user sudo previlage
--------------------------------------

sudo visudo 

jenkins ALL=(ALL:ALL)  NOPASSWD:ALL


sudo systemctl restart jenkins


STEP:5 Jenkins UI webpage
-----------------------------

Jenkins default path : /var/lib/jenkins

open url with public IP 

<PublicIP:8080>

password:

cat /var/lib/jenkins/secrets/initialAdminPassword

Login and install suggested plugins

Create Login credentials and start using Jenkins

STEP:6 Adding Git jobs 
--------------------------

Go to new Item in jenkins and Goto source code managemnet.

Add ssh keys for git 

in my laptop cat id_rsa

copy private Ip to jenkins credentials selection ssh with userkeys.


Git clone <URL> and select the ssh key to clone directly from git hub.









