* checking shells
 ```
   .echo $SHELL
   .echo $0
 ```
* change the normal user `eg:bash->csh`
 ```
 .cat /etc/passwd |tail -4
 .cat /etc/passwd |tail -4 |grep -i u1
 .usermod -s /bin/csh u1

 ```

* for root can be changed the user shell 
 ```
 .usermod -s /bin/bash <user_name>
 .usermod -s /bin/sh <user_name>
 .usermod -s /bin/nologin <user_name>
 ``` 
* normal user can login and how to know the user which shell are using currently and changing the own shell for sudo access
 ```
 .echo $SHELL
 .echo $0
 .chsh
    .Changing shell for u1.
     New shell [/bin/sh]
     /bin/bash
    .Password:
     Shell changed.
    .[u1@venu61 ~]$ echo $0
     -bash
 .echo $0
 ```
* if the user try to connect no-login into the access
 ```
 .checking the user account details 
  .cat /etc/passwd |grep -i <user_name>
  .chage -l u1
  .chage --help 

 ```
* echo command is printing the messages
 ```
 .echo -e "hello"
 .echo -e "hello \t hi"
 .echo -e "hello \n hi"
 .echo -e "hello \t\n\t hi"
 ```
* colouring the outputs by using `echo-command`
 ```
 .echo -e "\033[32m hello"
 .echo -e "\033[32m hello\nhi \033[0m"
 .echo -e "\033[32;40m hello\nhi \033[0m"
 . echo -e "\e[1;35;40m venugopal \e[0m"
 .echo -e "\e[32m hello\n\thi \e[0m"
  -e=>escape sequence
   m=>terminating escape sequence
   033=>enable colour code
   e=>enable colour code
 ```  
* 