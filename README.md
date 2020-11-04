### Jenkins+Nginx automatic deployment demo
### This project is supposed to demonstrate the automatic site checkout from git and deployment to web server by Jenkins upon successfull bild
### It will run two vagrant boxed, one for Web server and one for Jenkins.
Requirements:
  #### OS: 
   * Linux w/ kernel version 5.x or later
  #### Software:
   * vagrant v.2.2.10
   * git client (optionally)
  #### Harwdare minimum/recommended:
   * RAM: 4 GB / 8 GB
   * HDD: 8 GB
   * CPU @2Hhz / @3Hhz
   
#### How to use:

1 Clone this project to some directory on you host
 * git clone https://github.com/eadg1/test2-1
 
or download as zip archive and extract to target directory

2 Rename config.yml.sample to config.yml in the root directory of the project

3 Assign value to admin_user_pass (as plain text) in config.yml and save it

4 Navigate to /setup/files folder

5 Rename key.pub.sample and privatekey.sample to key.pub and privatekey accordingly

6 Navigate to your keypair location (cd ~/.ssh) or generate a keypair if you don't have one:
 * on linux: Create RSA keypair, leaving the passphrase empty (just press Enter)
 
   * ssh-keygen -t rsa
   
 * on other OS: please refer your OS documentation
 
 7 Copy and id_rsa.pub contents into 'key.pub' file , and id_rsa contents - into 'privatekey' file or simply copy files under designated name to  the /setup/files folder
 
 8 Navigate to root folder of the project and run 'vagrant up'
 
 9 Wait till boxes are up and running
 
 10 Navigate to http://192.168.2.10:8080 and login to Jenkins
 * username - jenkins, password - as assigned at step#3
 
 11 Wait till job run&execute (you may select build running on left and watch the process under 'Console output')
 
 12 Navigate to http://192.168.2.21/
  * You should see 'Hello World!' 
    
    
 
 
 
   