---
description: Linux可执行脚本.sh
---

# Shell Script

## File Structure

```sh
#! /bin/bash
# the first line start with #! 
#    specify the enviroment in which the script will be run

# some annotations

# logic code
```

## Variable assignment and use

```bash
#! /bin/bash

# create a variable and assign it a value
str="monday"

# use the variable
echo "today is : $str"
echo ${str}  #recommend
```

### Debug shell script

```sh
sh -x shell_file.sh: it will execute each step of the script and print and output it
    to the screen

result as below:
# debug shell script: successful execute
[root@localhost shell]# sh -x s1.sh 
+ str=monday
+ echo 'today is: monday'
today is: monday
+ echo monday
monday
```

### Variable Substitution

```sh
# to use "\" to escape
#! /bin/bash
str="100"
echo "RMB: ￥${str}"
echo "Dollar: \$ ${str}"
```

### Pass parameter to script

```sh
# in script, it can accept parameter as the format $1...$n
#! /bin/bash

# $0: script's name
echo \$0: $0
# $1: the first parameter
echo \$1: $1
# $#: the number of script parameters
echo \$#: $#
# $*: all parameters form a string
echo \$*: $*
# $@: each parameter is a string
echo \$@: $@
# $?: the return value of the previous command, 
#    0:execute successful, non 0:execute fail
echo \$?: $?
# $$: the pid of current progress
echo \$$: $$
```

### Quotation mark rules

```sh
#! /bin/bash

name=haha
# single qutoes: all character in single qutoes are common character
echo '$name'   # will print $name

# double qutoes: keep variable properties and replace it with value
echo "$name"  # will print haha

# inverted quotation marks: when a command is enclosed in inverted qutotation marks,
# the command will be execute and results will be the value of the expression
echo `date`  # will print Mon Dec 15 10:19:23 CST 2023
```

## Arrays

```bash
# constant list: elements are separated by spaces
arr1=("a1" "a2" "a3")

# define arrays by declare and initializes the element
declare -a arr2=("b1" "b2" "b3")

# define first and then assign the value to the element
declare -a arr3
arr3[0]="c1"
arr3[1]="c2"

# view the length of the array
echo ${#arr3[*]}

# read an array element
echo ${arr1[0]}

# delete an array element
unset arr1[0]
```

## Operator

```bash
-eq # equal
-ne # unequal
-lt # less than
-gt # greater than
-le # less than or equal to
-ge # greater than or equal to

==  # compare two strings to see if they are equal
!=  # compare two strings to see if they are unequal

```
