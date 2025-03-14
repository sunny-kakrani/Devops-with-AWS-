

## Jenkins Server Credentials :

  * __instance__ : t2.medium 
  
  * __Default User__ : ubuntu 

  * __username__ : admin

  * __password__ : admin

  * __port__ : 8080

##  Tomcat Server Credentials :

 * __instance__ : t2.micro
  
  * __Default User__ : ec2-user

  * __username__ : admin

  * __password__ : admin

  * __port__ : 8080

__NOTE: <mark> When the machine comes up in AWS, the public IP gets changed & we need to restart the Tomcat Server by calling sh startup.sh__

## SonarQube Server Credentials :

 * __instance__ : t2.medium
  
  * __Default User__ : ec2-user

  * __username__ : admin

  * __password__ : admin

  * __port__ : 9000

__NOTE:__ <mark>__When we shut down the EC2 machine in which Sonar Server is running , next time the IP of the machine will change & you have to login as a Sonar User to start the Sonar Server again.__</mark>
