### SED COMMAND:

* to print line number from a file by using `sed` command
  ```
  cat -n /etc/passwd |sed -n '10,15 p'
  ```
  ![preview](images/sed.PNG)
* to print odd numbers in a file
  ```
  cat -n /etc/passwd |head -10 |sed -n '/1~2 p'
  ```  
  ![preview](images/sed0.PNG)
* to print even numbers from a file   
  ```
  cat -n /etc/passwd |head -10 |sed -n '2~2 p'
  ```
  ![preview](images/sed1.PNG)
* to delete a lines from a file
  ```
  cat -n /etc/passwd |head -10 |sed '2 d'
  cat -n /etc/passwd |head -10 |sed '2 d'
  ```  
  ![preview](images/sed2.PNG)
* to delete a 2nd to last line 
  ```
  cat -n /etc/passwd |head -10 |sed '2 $d'
  ```  
  ![preview](images/sed3.PNG)
* to delete a word in file
  ```
  cat -n /etc/passwd |tail -10 |sed '/jonny/ d'
  ```  
  ![preview](images/sed4.PNG)
* to change the name old-name to new-name
  ```
  cat -n /etc/passwd |tail -10 |sed 's/jonny/venu/'
  ```  
  ![preview](images/sed5.PNG)
* if a word capital/small letters
  ```
  echo apple ant |sed -e 's/A/a/g'
  ```
* to change the name whole file as a same name
  ![preview](images/sed6.PNG)

### To editing configuration files by using `sed` command

* committed and un-committed lines

* cat /shells/sshd.config |grep -i dns
 ![preview](images/sed7.PNG)
* in conf file have a single word we can be search use this `sed '/UseDNS/`
* can be replace `yes/no`
 ![preview](images/sed8.PNG) `sed /UseDNS/s/yes/no/` 
* To un-commited line 
 ![preview](images/sed9.PNG)
* if a single word number of lines can be formed
 ![preview](images/sed10.PNG)
* if we use `sed  /^Password*/p`
 ![preview](images/sed11.PNG)  
*  if PasswordAuthentication yes  `sed '/^Password*/s/yes/no'`
 ![preview](images/sed12.PNG)
* word committed line # `sed /^Password*/s/^/#/`
 ![preview](images/sed13.PNG)
* word un-committed line #  `sed /UseDNS/s/#//`
 ![preview](images/sed14.PNG)

* configuration file `selinux`
 ![preview](images/sed15.PNG) 
*   cat /etc/selinux/config |grep -i selinux |sed -n '/^SELINUX*/p'
 ![peview](images/sed16.PNG)
*   `|sed  '/^SELINUX*/s/enforcing/permisive/'`
 ![preview](images/sed17.PNG)

### BOOT ORDER 
*  changing the system boot order timings 
  
  ```
   cat /etc/default/grub |grep -i grub_timeout
  ```
  ![preview](images/sed18.PNG)
* can change the boot timings
  
  ```
  cat /etc/default/grub |grep -i grub_timeout |sed '/grub_timeout/s/5/10/'
  ```  
  ![preview](images/sed19.PNG)
* committed the line
  ```
   cat /etc/default/grub |grep -i grub_timeout |sed '/sed grub_timeout/s/5/10/' ||sed '/GRUB_TIMEOUT/s/^/#/'
  ```
  ![preview](images/sed20.PNG)  

### changing the names and commited 
 ```
 cat /etc/password |grep -i preethi |sed '/preethi/s/preethi/arjun/' |sed '/preethi/s/^/#/'
 ```  
 ![preview](images/sed21.PNG)
* can also cut the based columns by using `sed-command`
  ```
   cat /etc/passwd |tail -3 |sed 's/preethi/venu/' |sed 's/^/#/' |cut -d: -f1,2,4
  ``` 
  ![preview](images/sed22.PNG)