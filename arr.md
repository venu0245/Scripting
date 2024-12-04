## Arrays
---------------
* Script for user name and assign a password by using `read-command` while typing the password printing on the sreen
* SheBang
 ```
 emp[0]=john
 emp[1]=jhone
 emp[2]=ali

 echo ${emp[0]}
 echo ${emp[1]}
 echo ${emp[*]}=>all employes
 echo ${emp[@]}=>all employes
 echo ${#emp[*]}=>total number of employes
 ``` 
 
 ```
 #!/bin/bash
 read -p "type your name: " name
 read -p "type your password: " pass
 echo -e "\nUser=\name\nPassword=$pass"
 wq!
 chmod +x script.s 
 ```
 ![preview](images/arry.01.PNG)

* script for to take user and location by using read command
 ```
 echo "please type your name"
 read name
 echo "please type your location"
 read loc
 echo "your name is $name"
 echo "your location $loc"
 wq!
 ```
 ![preview](images/arry.02.PNG) 

* script to create one line for user information
 ```
 #!/bin/bash
 echo -n "please type your name: "
 read name
 echo -n "please type your location: "
 read loc
 echo "your name is $name"
 echo "your name is $loc"
 wq!
 ```
 ![preview](images/arry.03.PNG)

* script for user information by using read command
 ```
 #!/bin/bash
 read -p "type your name: "
 read -p "type your loc: "
 echo "your name is $name"
 echo "your name is $loc"
 ``` 
 ![preview](images/arry.04.PNG)

* script for user name and password
```
read -p "type your name: " name
read -p "type your password: " pass
echo -e "\nUser=$name\npassword=$pass"
``` 
![preview](images/arry.05.PNG)

* script for user name and password (password not printing)
 ```
 read -p "type your name: " name
 read -s -p "type your password: " pass
 echo -e "\nUser=\nname\npassword=$pass"
 s--> security 
 ```
 ![preview](images/arry.06.PNG)
* script for mathemaic calculation 
  ```
  #!/bin/bash
  read -p "type first value: " a
  read -p "type secound value " b
  echo "Add=$(($a+$b))"
  echo "sub=$(($a-$b))"
  echo "mul=$(($a*$b))"
  wq!
  ```
  ![preview](images/arry.07.PNG)

### Special variales
* special variale 
 ```
 #!/bin/bash

echo '$0='$0
echo '$1='$1
echo '$2='$2
echo '$*='$*
echo '$@='$@
echo '$#='$#
echo '$$='$$
 wq!
 ```
 ![preview](images/arry.08.PNG)

* script for calculate taking input by using special variable
 ```
 #!/bin/bash
 a=$1
 b=$2
 echo "Add=$(($a+$b))"
 echo "Sub=$(($a-$b))"
 echo "Mul=$(($a*$b))"
 wq!
 ``` 
 ![preview](images/arry.09.PNG)


