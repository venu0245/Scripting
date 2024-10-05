### VARIABLES:
* variables starts with letters and not starts with numbers
  ```
  ram
  ram123
  ram_123
  ram_var
  ```
* properties:
  ```
  ro
  rw
  local
  global
  export-->local
  ```
* create a environmental variables for temporary
  ```
  name=car
  echo $car
  bash
  echo $car
  ```
  ![preview](images/usr0.PNG)  
* create a environmental variables for permanent
  ```
  ls -a
  .bashrc
  .bash_profile
  ```  
  ![preview](images/usr1.PNG)

* create a user and assign password it's own 

  ```
  vim test1.sh

  #!/bin/bash

  #script for creating a user by using variables
  
  user=ram
  
  echo "useradd sucessesful" $user
  useradd $user
  
  echo "password set successfully $pass"
  
  passwd $user
  .wq!
  .chmod +x test1.sh
  ./test1.sh
  ```
  ![preview](images/usr2.PNG)
  ![preview](images/usr3.PNG)

*  create a user and assign password automatically
  ```
  vim test2.sh
  #!/bin/bash

  #script for creating a user  and assign a password
  
  
   echo "useradd sucessesful ram"
   useradd ram
   
   passwd redhat@123
   
   echo "password set successfully ram"
  .wq!
  .chmod +x test1.sh
  ./test2.sh
  
  ```
  ![preview](images/usr4.PNG)   
* to changing the password for single attempt
  ```
  .passwd --help
     --stdin  read new tokens from stdin (root only)

     echo <passwd_name>|passwd <user_name> --stdin 

      echo red |passwd ram --stdin

     Changing password for user ram.
     passwd: all authentication tokens updated successfully.
  ``` 
  
  ```
  vim test3.sh
  #!/bin/bash

   #create a user and assign password  by using --stdin
   
   user=ram
   pass=red
   
   useradd $user
   echo "user $user add successfully"
   echo $pass |passwd $user --stdin
   
   echo "user $user passwd set successfully"

   .wq!
  .chmod +x test1.sh
  ./test3.sh
  ```    
  ![preview](images/usr5.PNG)
