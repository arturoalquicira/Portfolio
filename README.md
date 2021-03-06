Portfolio
===

Deployment Plan
===

### Setup Server
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

### Setup Apache2
1.- Use apt-get to install apache2
  * `sudo apt-get install apache2`
  
2.- Configure ServerName
  * `sudo vi /etc/apache2/conf-available/servername.conf`
  * And inside this we just need to add one line
  * `ServerName your-server-name`
  * Esc + :x

3.- Enable servername configuration
  * `sudo a2enconf servername`

4.- Reload the server
  * `sudo service apache2 reload`
  
5.- Go straight to **Git Hooks**
  
### Setup Github
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

4.- Copy SSH Key from id_rsa.pub file and paste it into SSH Keys under Account Settings of your GitHub
  * `less ~/.ssh/id_rsa.pub`
  * `:q` to exit

5.- Check if github works
  * `ssh git@github.com`
  * It will kick you out

Git Hooks and Production Deployment
===

### Configure Git Hooks 
1.- Go to folder ../var/www/
  *  `sudo chown username ./html/`
  * Go to folder ../var/www/html
  *  `ls -l`
  *  `cd html/`
  *  `rm index.html`
 
2.- Go back to **../var** directory and create "repos" folder
  * Inside ../var folder:
  * `sudo mkdir repos`
  * `sudo chown username repos`
  *  `cd repos/`

3.- Create a '.git' folder in your "repos" folder 
  * `mkdir folder-Name.git` (site-prod.git is recommendable as a name)
  *  `cd folder-Name.git`

4.- Inside your '.git' folder initialize bare git and move into "/hooks" folder
  * `git init --bare`
  * `cd hooks/`

5.- Inside "/hooks" folder, create this executable file
  * `pico post-receive`
  *  Then type the following lines
    * `#!/bin/sh`
    * `GIT_WORK_TREE=/var/www/html git checkout -f`
    * ctrl + x *to exit*
  * `chmod +x post-receive` **you need this path**
  
Setup Sourcetree
---

1.- Create *local repository*

2.- Create empty folder with the name of the server

3.- Go to respository settings inside the local repo

4.- Add remote repository and insert a path like this one:

5.- `ssh://pipo@104.259.91.62/var/repos/site-prod.git`

6.- start commiting and pushing to master



Continue *only* if you are using Github|Git
---

6.- Add remotes - Open a new terminal window and narrow down to your project folder or directory
  * `git init`
  * `git remote add varName(name of the server) ssh://userName@104.31.1.1/var/repos/folderName.git`
  * `git push varName master`
  

 
  


