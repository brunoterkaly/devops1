# Jenkins

Overview of CI/CD with Jenkins.


	```java
	#!/usr/bin/env groovy
	
	/* Only keep the 10 most recent builds. */
	properties([[$class: 'BuildDiscarderProperty',
	                strategy: [$class: 'LogRotator', numToKeepStr: '4']]])
	                
	echo "hello from pipeline"
	node {
	  stage 'Stage Checkout'
	  //git url: 'https://github.com/brunoterkaly/spring-boot-sample-atmosphere.git'
	  git url: 'https://github.com/brunoterkaly/httpservice.git'
	
	  deleteDir()
	  
	  stage 'Build'
	 //branch name from Jenkins environment variables
	 //sh 'gradle build'
	 // sh "./gradlew clean build"
	 sh 'gradle build --info'
	 sh 'python3 -V'
	 // sh './gradlew build --info'
	 sh 'docker --version'
	 
	 git url: 'https://github.com/brunoterkaly/devops.git'
	
	 sh 'python3 hello.py'




	}


#### Some useful commands


	sudo /etc/init.d/jenkins start


#### Each job gets config.xml

Uses XStream, GUI uses the Jelly framework.

Turn off security with "useSecurity=false" in config.xml.

	sudo apt-get install nginx
	/etc/init.d/nginx status
	/etc/init.d/nginx restart
	vim /usr/share/nginx/html/index.html
	vim /var/www/html/index.nginx-debian.html

	vim /etc/nginx/nginx.conf
	vim /etc/nginx/sites-available/default
	server {
        listen 8088 default_server;
        listen [::]:8088 default_server;

#### Setup reverse proxy for Jenkins using NGINX

- service ssl requests and pass to multiple Jenkins servers as http requests
- 

from docker import Client
cli = Client(base_url='tcp://127.0.0.1:2375')

- sudo usermod -aG docker jenkins
- vi /lib/systemd/system/docker.service

-     
- sudo gpasswd -a jenkins docker
- docker build -t myapp .
- curl http://127.0.0.1:2375/info

- /etc/group 
	- Group account information. 
- /etc/gshadow 
	- Secure group account information. 
- /etc/passwd 
	- User account information. 
- /etc/shadow 
	- Secure user account information. 
 
- $> cat /etc/group
	- jenkins:x:128:
	
 usermod -m -d /newhome/username username
vi /etc/default/useradd
HOME=/iscsi/user
useradd vivek
passwd vivek
finger vivek

finger jenkins
Login: jenkins                          Name: Jenkins
Directory: /var/lib/jenkins             Shell: /bin/bash
Never logged in.
No mail.
No Plan.

$> finger jenkins
Login: jenkins                          Name: Jenkins
Directory: /var/lib/jenkins             Shell: /bin/bash
Never logged in.
No mail.
No Plan.

/etc/adduser.conf


 get tom ids 
id jenkins
# see login info
grep ^jenkins: /etc/passwd
# see group info
grep ^jenkins: /etc/group 
# See home dir permissions
ls -ld /home/jenkins/
# See process owned by jenkins user/group
ps aux | grep jenkins
ps -u jenkins

/root/github/devops

python listimages.py
bash checkin.sh

python listimages.py
Cannot connect to the Docker daemon. Is the docker daemon running on this host?

python jenkins subprocess Cannot connect to the Docker daemon. Is the docker daemon running on this host?
Giving permission to /var/run/docker.sock
sudo usermod -aG docker jenkins



How to verify a user is part of a group



$> grep ^docker /etc/group
docker:x:120:root,jenkins





export VARNAME="my value" 

gksudo gedit /etc/environment
printenv @TERM


export JAVA_HOME=/usr/lib/jvm/jdk1.7.0
export PATH=$PATH:$JAVA_HOME/bin



export DOCKER_HOST=tcp://10.3.0.4:2375
echo DOCKER_HOST=tcp://10.3.0.4:2375
env | grep DOCKER


## Workflow

cd ~/github/devops

$> ls
checkin.vbs  do.vbs  hello.py  listimages.py  README.md

"# devops1" 
