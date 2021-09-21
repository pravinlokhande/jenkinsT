##Jenkins Installation on CentOS 8 [https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos]

   >  yum update -y
   
   # To install Jenkins from official docs
   >  wget -O /etc/yum.repos.d/jenkins.repo     https://pkg.jenkins.io/redhat-stable/jenkins.repo
   >  rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
   >  yum upgrade
   >  yum install epel-release java-11-openjdk-devel
   >  yum install jenkins
   >  systemctl daemon-reload
   
   # To enable Jenkins service
   >  ls /var/lib/jenkins/
   >  systemctl start jenkins
   >  systemctl status jenkins
   >  systemctl enable jenkins
   
   # Open browser and enter <IP(where jenkins installed)>:8080/
     If page is not openining then change the firewall config and enable port 8080.

   # To remove firewall restrictions:
   >  systemctl status firewalld
   >  firewall-cmd --permanent --add-port=8080/tcp
   >  firewall-cmd --reload
   
   # Now, refresh the browser page
     Then you will be asked for Initial Admin password and that you will get it from /var/lib/jenkins/secrets/initialAdminPassword
   >  cat /var/lib/jenkins/secrets/initialAdminPassword
     Copy this password and add in the browser.
     This is the first login password, then you can remove the initial admin password file for security purpose.
   
   # Select Install Suggested Plugins
     And wait till you get new user creation page
   
   # Create one user with your name and choose a simple password (ex. pravin:pravin)
   
   # Once, you create user. It will navigate to Instance Configuration page
     This is your jenkins URL.
     Click on save
   # Jenkins is Ready!
     Your jenkins setup is complete.


