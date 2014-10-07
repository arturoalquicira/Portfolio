Portfolio
===

Deployment Plan
===

###Setup Server
1.- Create a new droplet

2.- Acces via terminal 
  * (ex. ssh root@118.0.0.1)
  
3.- Enter root password

4.- Create  a user name and password 
  * adduser USERNAME
  
5.- Add your new username to the sudo group 
  * adduser USERNAME sudo
  
6.- Exit 

###Setup Apache2
1.-Use apt-get to install apache2
  * sudo apt-get install apache2
  

###Setup Github
1.- Use apt-get to install git-core
  * sudo apt-get install git-core

2.- Configure Git
  * git config --global user.name “NAME”
  * git config --global user.email Your@Email.com

3.- Create SSH Keys for Github Access
  * ssh-keygen -t rsa -C ”YourEmail@example.com”
  * Enter a passphrase

4.- Copy github key from id_res.pub file and paste it into SSH keys 


