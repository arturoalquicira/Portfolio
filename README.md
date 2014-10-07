Portfolio
===

Deployment Plan
===

###Setup Server
1.- Create a new droplet

2.- Acces via terminal 
  * (ex. `ssh root@118.0.0.1`)
  
3.- Enter root password

4.- Create  a user name and password 
  * `adduser USERNAME`
  
5.- Add your new username to the sudo group 
  * `sudo adduser USERNAME sudo`
  
6.- `exit`

7.- Acces via terminal 
  * (ex. `ssh username@118.0.0.1`)
  
8.- Enter username password

9.- Run commands to update your server
  * `sudo apt-get update`
  * `sudo apt-get upgrade`
  * `sudo apt-get update`

###Setup Apache2
1.-Use apt-get to install apache2
  * `sudo apt-get install apache2`
  * 
2.- Configure ServerName
  * `sudo pico /etc/apache2/conf.d/security`
  * Below "< Directory />" add the following line:
    * `ServerName theNameOfTheServer`
  * `sudo service apache2 restart`
  * Uncomment all from <Directory> to < Directory /> and add `Options FollowSymLinks` at the end of the list
  

###Setup Github
1.- Use apt-get to install git-core
  * `sudo apt-get install git-core`

2.- Configure Git
  * `git config --global user.name “NAME”`
  * `git config --global user.email Your@Email.com`
  * `git config --list`

3.- Create SSH Keys for Github Access
  * `ssh-keygen -t rsa -C ”YourEmail@example.com”`
  * **Don't do anything and hit enter**
  * Enter a passphrase
  * Re-enter a passphrase

4.- Copy github key from id_res.pub file and paste it into SSH keys under Account Settings 
  * `less ~/.ssh/id_rsa.pub

5.- Check if github works
  * `ssh git@github.com`
  * It will kick you out


  


