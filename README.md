######MAVEN##########



$sudo apt update
$sudo apt install maven
$maven -version
$mkdir csm
$cd csm
$archetype:generate
	group id : com.Hello
	artifactid : csmdevops
	version : 1.0-SNAPSHOT
	package : com.Hello.app
$tree
$cd csmdevops
$mvn validate
$mvn compile
$mvn test
$mvn verify
$mvn install
$tree
$cd target
$java -cp csmdevops-1.0-SNAPSHOT.jar com.Hello.app.App



#########ANSIBLE############



$sudo apt update
$sudo apt install ansible
$ansible -version
$mkdir ~/ansible
$cd ~/ansible
$touch hosts.ini
$nano hosts.ini
	[local]
	localhost ansible_connection=local
$touch local_playbook.yml
$nano local_playbook.yml
	---
	-name: Install Nginx on local Machine
	  hosts: local
	  become: yes
	  tasks:
	    -name: Ensure Nginx is installed
	      apt:
	        name: nginx
	        state: present
$ansible-playbook -i hosts.ini local_playbook.yml
$systemctl status nginx
$echo nano /etc/nginx/sites-available/default
$sudo systemctl restart nginx
$ansible -version



############GIT#############



$sudo apt update
$sudo apt install git
$mkdir csm
$cd csm
$git config --global user.name ""
$git config --global user.email "" 
$git config --list
$git clone "repo link"
$cd repo name
$ls
$touch g1
$git status
$git commit -m "File created"
$git push -u origin main
$git remote set-url origin https://tokenlink@github
