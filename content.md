# DevOps Project

## Jenkins Installation

1. Start Amazon EC2 instance with internet access and SG with port 8080 open for internet

2. Jenkins installtion guide for Liunx (Red Hat and CentOS): https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos. Use LTS (Long-Term Support) release

	sudo wget -O /etc/yum.repos.d/jenkins.repo \
	    https://pkg.jenkins.io/redhat-stable/jenkins.repo
		
	sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
	
	sudo yum upgrade
	
	sudo amazon-linux-extras install epel -y
	
	sudo amazon-linux-extras install java-openjdk11 -y 
	
	sudo yum install jenkins -y
	
	sudo systemctl daemon-reload

3. Starting Jenkins

	sudo systemctl start jenkins
	
	sudo systemctl status jenkins
	
4. Accessing Jenkins

	It is accessed: http://YOUR-SERVER-PUBLIC-IP:8080
	
	Unlock jenkins using password from location: /var/lib/jenkins/secrets/initialAdminPassword
	
	Start using jenkins without any installations. can be done later
	
	Change login password: admin > Configure 
	
5. Configure java path

	Firstly find java path on the instance in the path: /usr/lib/jvm. Then add this as JAVA_HOME in .bash_profile file
	
	vi ~/.bash_profile
	
	JAVA_HOME=/usr/lib/jvm/jdk-file-name
	
	PATH = $PATH:$HOME/bin:JAVA_HOME
	
	Manage Jenkins > Global Tool Configuration > Add JDK
	
	




