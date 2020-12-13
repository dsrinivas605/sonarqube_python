# Pre-Requisites:
    - Install Java
    - Install Git
    - Install Jenkins
    - Install sonarqube
    - Install sonar-scanner
# Install Jenkins
    sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins.io/redhat-stable/jenkins.repo
    sudo rpm --import http://pkg.jenkins.io/redhat-stable/jenkins.io.key
    sudo yum install jenkins -y
    service jenkins start
# Sonarqube installation
  [Sonarqube installaton](https://github.com/Naresh240/sonarqube-installation.git)
# Instll sonar-scanner
    cd /opt
    wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.4.0.2170-linux.zip
    unzip sonar-scanner-cli-4.4.0.2170-linux.zip
# Integrate Sonarqube with jenkins
1. Add sonarqube plugin 
2. Add SonarQube servers with in jenkins
   - Need to create authentication token with in Sonarqube server
   
     ![image](https://user-images.githubusercontent.com/68885738/90910319-bebffd00-e3f4-11ea-8590-c9ae9018973e.png)
   
   - Need to create webhook with in Sonarqube server (use Jenkins server URL)
    
    ![image](https://user-images.githubusercontent.com/68885738/90953421-06906400-e489-11ea-9f1d-859b3b9fa7b8.png)
        
     Click on My Account
     
     ![image](https://user-images.githubusercontent.com/68885738/90910508-0ba3d380-e3f5-11ea-918a-1234e695ba01.png)
     
     Fill details and click on create
     
     ![image](https://user-images.githubusercontent.com/68885738/90953480-80285200-e489-11ea-8ec1-0eedb4635efb.png)
     
     select security and give some name for token and then click on Generate
3. Add SonarQube servers details with in "configure system"

![image](https://user-images.githubusercontent.com/68885738/90910714-689f8980-e3f5-11ea-889c-68e63b8302ce.png)

Name: sonar-scanner
Server URL: http://54.210.37.165:9000/
Server authentication token: (Create secret text with authentication token)

4. Add SonarQube Scanner with in "Global Tool Configuration"

![image](https://user-images.githubusercontent.com/68885738/90910959-dea3f080-e3f5-11ea-8d79-6062bff26d25.png)
