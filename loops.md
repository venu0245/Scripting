### Loops 
#### Infinite Loop
 .while loop
 .until loop

* while loop
 .execute when condition is `true`
* until loop
 .execute when condition is `false` 
##### WHILE-LOOP:
* script for while loop
 
 ```
 read -p "number of iteratons  " i
  while [ $i -gt 0 ]
  do
  echo "iteration number $i "
  done
 ```
* not sleep 1  => number of iterations can be generated fastly and every secound generated new process id 
 
 .bash -x scriptxx.xx
 . ./scriptxx.xx 

 ```
 #!/bin/bash
 #script for while-loop

 read -p "number of iteratons  " i
  while [ $i -gt 0 ]
  do
  echo "iteration number $i "
  sleep 1
  done
 ```
* sleep 1 =>slow process iterations can be generated 

* script for while loop geaterthan 0 
 ```
 #!/bin/bash
#script to use while loop

read -p "number of iterations: " p

while [ $p -gt 0 ]
do
        echo "iteration number $p "
        sleep 1

        p=$(($p-1))
done

 ```
* command-line can run any command
 ```
 while true 
 do
 ps
 sleep 1
 done
 ``` 
#### UNTIL-LOOP:
* script for until-loop  
 ```
#!/bin/bash
#script to use until_loop

read -p "number of iterations: " p

until [ $p -gt 0 ]
do
        echo "iteration number $p "
        sleep 1

        p=$(($p-1))
done

 ```
 p=$(($p-1))=>reducing the iteration number for 0 value

* command-line can run any command
 
 ```
 until false
 do
 date
 sleep 1
 done
 ```
 #### FINITE-LOOP:

* for-loop for mathematics
 ```
 #!/bin/bash
#script for loop-statement

calc()
{
        for op in ADD SUB MUL DIV
        do
                case $op in
                        ADD)echo "Add=$(($a+$b))" ;;
                        SUB)echo "Sub=$(($a-$b))" ;;
                        MUL)echo "Mul=$(($a*$b))" ;;
                        DIV) echo "Div=$(($a/$b))" ;;
                esac
        done
}

read -p "a value: " a
read -p "b value: " b
if [ -z "$a" -o  -z "$b" ];then
        echo "invalid input"
        exit
fi
if [ -e "$a" -o  -e "$b" ];then
        echo "invalid input"
        exit
fi

calc

 ``` 
* script for select-loop for mathematics
 
 ```
 #!/bin/bash
#script for loop-statement

calc()
{
        select op in ADD SUB MUL DIV EXIT
        do
                case $op in
                        ADD)echo "Add=$(($a+$b))";;
                        SUB)echo "Sub=$(($a-$b))";;
                        MUL)echo "Mul=$(($a*$b))";;
                        DIV)echo "Div=$(($a/$b))";;
                        EXIT)echo "existing"
                                exit;;
                esac
        done
}

read -p "a value: " a
read -p "b value: " b
if [ -z "$a" -o -z "$b" ];then
        echo "invalid input"
fi
if [ -e "$a" -o -e "$b" ];then
        echo "invalid input"
fi
calc

 ```
* adding users by using for-loop
  
 ```
 for p in user1, user2,user3
 do
 useradd $p
 done
 ```
* delete the users by using for-loop
 ```
 for p in user1, user2, user3
 do
 userdel $p
 done
 ``` 

* select-loop for prompt status
  
  PS3=>prompt status
 ```
 #!/bin/bash
#script for select-loop ps3
calc()
{
        PS3="select an option: "
        select op in ADD SUB MUL DIV EXIT
        do
                case $op in
                        ADD)echo "Add=$(($a+$b))";;

                        SUB)echo "Sub=$(($a-$b))";;
                        MUL)echo "Mul=$(($a*$b))";;
                        DIV)echo "Div=$(($a/$b))";;
                        EXIT)echo "existing"
                                exit;;
                esac
        done

}

read -p "a value: " a
read -p "b value: " b

if [ -z "$a" -o -z "$b" ];then
        echo "invalid"
fi

if [ -e "$a" -o -e "$b" ];then
        echo "valid"
fi

calc

 ```

#### GETOPTS:
* Getopts runs under the while_loop
 ```
 #!/bin/bash
#script for getopts

while getopts a:b:o: op
do
        case $op in
                a)a=$OPTARG ;;
                b)b=$OPTARG ;;
                o)o=$OPTARG ;;
                \?)echo "invalid argument"
                        exit ;;
        esac
done

echo -e "a=$a\nb=$b\no=$o"
 ```
* ./script05.sh -a 10 -b 30 -o ADD

* script for select the option and calculate the a and b values
 
 ```
 #!/bin/bash
#script for getopts

while getopts a:b:o: op
do
        case $op in
                a)a=$OPTARG ;;
                b)b=$OPTARG ;;
                o)o=$OPTARG ;;
                \?)echo "invalid argument"
                        exit ;;
        esac
done

echo -e "a=$a\nb=$b\no=$o"

 case $o in

         ADD)echo "Add=$(($a+$b))";;
         SUB)echo "Sub=$(($a-$b))";;
         MUL)echo "Mul=$(($a*$b))";;
         Div)echo "Div=$(($a/$b))";;
         *)echo "exiting"

 esac

 ```
*  ./script05.sh -a 10 -b 30 -o ADD

 

