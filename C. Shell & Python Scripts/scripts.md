## Linux Architecture :

* <mark>__Application -> Shell -> Kernel -> Hardware__  

 => When we execute any command in linux then Shell will process our command execution.

 => Shell will verify command syntax is valid or not. 

 => Shell will convert our command into __'kernel'__ understandable format 

 => Kernel is responsible to communicate with Hardware components. 
 
 => Kernel is the mediator between Shell and Hardware. 
 
 => Shell is mediator between __'user' and 'kernel'__ 

 

## Print all shells of linux machine 

* __$ cat /etc/shells__
 
* we can print the default shell of the linux machine by the below command , the default shell is __/bin/bash__

  * __$ echo $SHELL__
 
 

 

## What is Shell Scripting ? 

=> Shell will act as mediator between Users and Kernel. Shell will convert commands into kernel understandable format. 
 
=> Scripting means executing set of commands using a file. 
 
__The process of executing set of commands available in the file using SHELL is called as Shell Scripting.__
 
=> Shell Scripting is used to automate our daily routine works. 
 
=> Shell Script file will have .sh extension 

=> Below is the command to execute shell script file 
   
   * __$ sh `<filename>`__


__<mark>Script-1 : work.sh__

```sh
#! /bin/bash 
whoami 
pwd 
date 
```
__NOTE:__ you can run the above script by executing __sh work.sh__

__<mark>Script-2 : msg.sh__ 

```sh
#! /bin/bash 
 

echo 'Hello World' 
echo 'Welcome to DevOps World' 
echo 'DevOps is very interesting'
``` 

__<mark>Script-3 : NameDemo.sh__
 
```sh
#! /bin/bash 
 

echo 'Enter Your Name' 
read a 
echo "Good Evening $a" 
```

__<mark>Script-4 : Sum.sh__
 
```sh
#! /bin/bash 
 

a=10 
b=20 
 

c=$(($a+$b)) 
 

echo "Sum is : $c" 
```
 
__<mark>Script-5 : DynamicValSum.sh__
 
```sh
#! /bin/bash 
 

echo "Enter First Number" 
read a 
 

echo "Enter Second Number" 
read b 
 

c=$(($a+$b)) 
 

echo "Result : $c"
``` 
## What are Variables in Shell Scripting  ?
 
* Variables are used to store the data 

* Variables are divided into 2 types 
  
  * __Environment Variables__ (System Variables - Already Defined) 
  * __User Defined Variables__ (We will create these variables) 
 

__NOTE:__  To access value of variable we will use '$' symbol. 

 

## Command Line Arguments : 
 
* The arguments which we will pass to script file at the time of execution. 
 
   * __Ex:  sh demo.sh ashokit 30__ 
 
=> We can access command-line args in script file like below 
 

   * __$#__ - No.of args 
 
   * __$0__ - script file name 
   
   * __$1__ - First Cmd arg 
   
   * __$2__ - Second Cmd arg 
   
   * __$3__ - Third Cmd Args 
   
   * __$*__ - All cmd args 

__<mark>Script-6 : DynamicValSum.sh__ 

```sh
#! /bin/bash 

result=$(($1+$2)) 

echo "Sum is : $(($1+$2))" 

Run : sh DynamicValSum.sh 10 20 
```
* We have 2 options to pass dynamic values to shell script file 

  *  __Using 'read' command__

  *  __Using cmd args__ 

## Conditional Statements ( if - elif - else ) 

* Conditional Statements are used to execute 'commands' one time based on condition 

 

 
```sh
if [ condition ] 
then 
   statements 
else 
   statements 
```

__<mark>Script-7 : if-else.sh__

```sh 
#! /bin/bash 

echo "Enter Name" 
read name 

if [ $name == 'john' ] 
then 
   echo "Hi" 
else 
    echo "Bye" 
fi 
```
 
__<mark>Script - 8 : if-elif-else.sh__ 

```sh 
#! /bin/bash 

echo "Enter Name" 
read name 

if [ $name == 'john' ] 
then 
   echo "Hi $name" 

elif [ $name == 'smith' ] 
then 
   echo "Hello $name" 

else 
    echo "Bye $name" 
fi 
```
__<mark>Script - 9 : if-elif-else.sh__

```sh 
#! /bin/bash 

echo "Enter first number" 
read a 

echo "Enter second number" 
read b 

if [ $a -gt $b ] 

then 
   echo "$a is greater than $b" 

elif [ $b -gt $a ] 
then 
   echo "$b is greater than $a" 

else 
   echo "Both are equal" 

fi 
```
## Iterative Statements LOOPS (for, while) : 

* To print "hi" 5 times we will write script like below:

  * echo "hi" 
  * echo "hi" 
  * echo "hi" 
  * echo "hi" 
  * echo "hi" 

* If we want to print "hi" for 1000 times, can we write echo for 1000 times ? __Not recommended__ 

* To execute same command multiple times then we will use "Loops" 

* We can use two types of loops while writing the shell script: 

  * __Range Based Loop  (Ex: for loop)__ 
  * __Conditional Based Loop (Ex: while loop)__

__NOTE:__ <mark>Print "hi" message 10 times (Here we know the range to print msg - we can use 'for' loop) 

__NOTE:__ <mark>Print "good night" message till 10 PM (Here we don't range, but we know condition - we can use while loop) 
 
__<mark>Script-10 : for-loop1.sh__ 

```sh
#! /bin/bash 

for (( i=1 ; i<=10; i++ )) 
do 
  echo "hi" 
done 
```
<mark>__Script-11 : for-loop2.sh__ 

```sh 
#! /bin/bash 

for (( i=1; i<=10; i++ )) 
do 
  echo "$i" 
done 
```
__<mark>Script-12 : while-loop.sh__ 

```sh 
#! /bin/bash 

i=10 
while [ $i -ge 1 ] 
do 
  echo "$i" 

let i--; 
done
``` 

 

## Functions/Methods : 

 * Functions are used to perform some action / task 
 
 * The big task can be divided into smaller tasks using functions 
 
 * Using functions we can divide our tasks logically 
 
 * Functions are re-usable 

```sh 
function functionName ( ) { 

// function body 
} 
 

# calling function 
functionName
``` 
 
<mark>__Script - 13 : fun1.sh__

```sh
#! /bin/bash 
 
function welcome ( ) { 
 

   echo "this is line 1" 
   echo "this is line 2" 
   echo "this is line 2" 

} 
 

# calling function 
welcome
``` 
__<mark>Script-13 : fun2.sh__
 

 
```sh
#! /bin/bash 

 
function welcome() 

{ 

        echo "Welcome to $1" 

} 

welcome java 

welcome linux 

welcome maven 

welcome gradle 
```
__<mark>Script - 14 : Read File name then print content of that file.__
 
```sh
#! /bin/bash 
 

function readFileData ( ) { 
   echo "Enter file name to read" 
   read filename 
   cat $filename 
} 

# calling function 
readFileData 
```

__NOTE:__ 'cat' command is used to print the content that is available in the file, but echo command is used for the message printing purpose . 

<mark>__Script - 15 : Read File name as cmd arg then print content of that file.__

```sh
#! /bin/bash 
 

filename=$1   [ We have received the parameter that we are passing from the command prompt already and now we are using in the function ] 

  

function readFileData ( ) { 
     cat $filename 
} 

# calling function 
readFileData 
```
 
__<mark>Script-16: Check file exists or not__

```sh
#! /bin/bash 

echo "enter filename" 
read filename 
 

if [ -f "$filename" ] ; then 
echo "File already exist" 
else 
echo "File not exist, hence creating..." 
touch $filename 
echo "file created...." 
fi
``` 

__<mark>Script-17: Check directory exists or not__

```sh
#! /bin/bash 
 

echo "Enter directory name" 
read dirname 
if [ -d "$dirname" ] ; then 
        echo "Directory exist" 
else 
        echo "directory not available, hence creating.." 
        mkdir $dirname 
        echo "directory created" 
fi 
```

__NOTE:__  We can give any directory/file location for checking the file/directory exists or not. 

## What is CRON & CROND? 

* Cron is a utility in Linux which is used to schedule jobs execution 
 
* In Realtime we will have several jobs for execution on __daily / weekly / monthly / yearly basis__ 

  * Take Backup of files 
  * Delete temp files 
  * System Maintenance 

__<mark>USECASE:__ 

   * Execute shell script file for every 5 minutes. 
 
__NOTE:__ Instead of human executing script file for every 5 minutes, we can schedule script file execution using __CRON.__
 
__What is CROND ?__ 

* In Linux machine CROND is a daemon process ( background ) which will check scheduled CRON JOBS for every minute.  
 
* If any job is scheduled then CROND will execute that job based on given schedule. 

 

__CRON JOB SYNTAX :__

  *  \* __* * * * *  < command / script-file >__ <mark>(Read Cron Expression from left side always)

* first * will represent minutes ( 0 - 59 ) 

* second * will represent hour ( 0 - 23 ) 

* third * will represent day of month ( 1 - 31 ) 
 
* fourth * will represent month of year ( 1 - 12 ) 
 
* fifth * will represent day of week ( 0 - 6, SUNDAY - SATURDAY ) 
 
__Sample Cron Expressions :__ 

 * __Run for every 15 mins :__    */15 * * * *  task.sh 

 * __Run every day @5 am :__       0 5 * * *  task.sh 
 
 * __Run every day @5 pm :__     0 17 * * * task.sh 
 
 * __Run every month first day @9 am :__ 0 9 1 * * task.sh 

__What is crontab file ?__

* In Linux for every user account one crontab file will be available 
* crontab file is used to configure cronjobs for execution 
 
* Open crontab file 
   * __$ crontab -e__
 
* Display cronjobs schedules 
  * __$ crontab -l__ 
 
* Remove crontab file 
  * __$ crontab -r__
 
* Check Cron Status 
  * __$ sudo systemctl status cron__ 
 

__CRON JOB Practice:__ 

* Launch Linux Machine with Ubuntu AMI (Because In Amazon Linux , the support for CRON Jobs is not present] 

* Connect with Ubuntu VM using MobaXterm/Putty 

* Create shell script file (task.sh) like below 
 
   * __$ vi task.sh__ 
 
 

```sh
#! /bin/bash 

touch /home/ubuntu/f1.txt 
touch /home/ubuntu/f2.txt 
```
* Provide execute permission for script file 
 
  * __$ chmod +x task.sh__

* Open crontab file and configure job schedule 

  * __$ crontab -e__ 

__NOTE:__ Enter below cron job in crontab file 

__<mark>*/1 * * * * /bin/bash  /home/ubuntu/task1.sh [Execute the shell script in every 1 minute ]__

* Save and close crontab file ( ctrl + x ) 

* Check files creation in pwd 
   * __$ ls -lrt__

__NOTE:__ We can observe f1.txt and f2.txt files got created even after deleting as well .