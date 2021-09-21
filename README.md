### Jenkins Installation on CentOS 8

 55  yum update -y
   # To install Jenkins from official docs
   56  wget -O /etc/yum.repos.d/jenkins.repo     https://pkg.jenkins.io/redhat-stable/jenkins.repo
   57  rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
   58  yum upgrade
   59  yum install epel-release java-11-openjdk-devel
   60  yum install jenkins
   61  systemctl daemon-reload
   
   # To enable Jenkins service
   63  ls /var/lib/jenkins/
   64  systemctl start jenkins
   65  systemctl status jenkins
   66  systemctl enable jenkins
   
   # To remove firewall restrictions:
   67  systemctl status firewalld
   68  firewall-cmd --permanent --add-port=8080/tcp
   69  firewall-cmd --reload
   
   70  ls /var/lib/jenkins/
   71  cat /var/lib/jenkins/secrets/initialAdminPassword
   
### use this password for first time login 
## Select Install Suggested Plugins
## wait till you get new user creation page 
## Create one user with your name and choose a simple password (ex. rps)
