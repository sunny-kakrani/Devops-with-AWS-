
## How to connect with the linux ec2 machines created in the AWS Cloud:

  * You will get the public IP of the machines and through that IP , you can connect from anywhere .

  ![alt text](A.%20Basic%20Devops/connect.png)

  * __instance :__ t2.micro

  * __Default User:__ ec2-user

## Nexus Server Credentials:

* __instance__ : t2.medium

* __Default User__ : ec2-user

* __username__ : admin

* __password__ : admin

* __port__ : 8081

__NOTE:__ <mark>__When the machine is up in the EC2 -Instance . No need to start the nexus via executing some commands as a nexus user . We can directly access nexus server with the IP and Port.__</mark>

__NOTE:__<mark> __When the ec2 machine gets restarted , Public IP will change and we have to use that new Public IP where we are making the connection.__<mark>

## SonarQube Server Credentials :

 * __instance__ : t2.medium
  
  * __Default User__ : ec2-user

  * __username__ : admin

  * __password__ : admin

  * __port__ : 9000

__NOTE:__ <mark>__When we shut down the EC2 machine in which Sonar Server is running , next time the IP of the machine will change & you have to login as a Sonar User to start the Sonar Server again.__</mark>

__NOTE:__<mark> __When the ec2 machine gets restarted , Public IP will change and we have to use that new Public IP where we are making the connection.__<mark>

##  Tomcat Server Credentials :

 * __instance__ : t2.micro
  
  * __Default User__ : ec2-user

  * __username__ : admin

  * __password__ : admin

  * __port__ : 8080

__NOTE: <mark> When the machine comes up in AWS, the public IP gets changed & we need to restart the Tomcat Server by calling sh startup.sh__

## Jenkins Server Credentials :

  * __instance__ : t2.medium 
  
  * __Default User__ : ubuntu 

  * __username__ : admin

  * __password__ : admin

  * __port__ : 8080



