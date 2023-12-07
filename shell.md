## SHELL SCRIPTING

#### INTRODUCTION

* shell script runs under bash shell
* total shells installed

  ```
  cat /etc/shells
  ```
  ![preview](images/shell0.PNG)

* as a admin(root) user can change the user shell 

  ```
  grep -i u1 |tail /etc/passwd
  usermod -s /bin/sh u1
  usermod -s /bin/bash u1
  ```
* user can check the own shell

 ![preview](images/shell1.PNG)
* normal user can also the change shell `chsh` & `passwd` for the login user

* grep u1 |tail -2 /etc/passwd 
* echo $0
 ![preview](images/shell2.PNG)

* sampple script
  ```
  vim tesh.sh
   who
   pwd
   date
   parted -l
   wq!
  ``` 
* chmod +x tesh.sh
  bash test.sh
  sh test.sh
  ./test.sh
  ![preview](images/test0.PNG)

### SHEBANG (#!) #SHARP !BANG

*  .Comment `cannot see the information with execute script`
   .uncomment `can only see the information with execute script`

```
#! /bin/bash
#! /bin/perl
#! /bin/python
``` 

  ![preview](images/shell3.PNG)
  ```
  chmod +x test1.sh
  ./test1.sh
  as root user we can run the script directly bash,sh
  ```
  ![preview](images/shell4.PNG)

* ### ECHO Command
  `echo` command printing the message
   e escape sequnce
   n new line
   t tab space
  ```
    [root@localhost ~]# echo hello
  hello
  [root@localhost ~]# echo -n hello
  hello[root@localhost ~]# echo -e hello\nworld
  hellonworld
  [root@localhost ~]# echo -e "hello\nworld"
  hello
  world
  [root@localhost ~]# echo -e "hello\tworld"
  hello   world
  
  ```
* colouring the o/p messages `echo -e \033 & \e`
  ![preview](images/shell5.PNG)

 






