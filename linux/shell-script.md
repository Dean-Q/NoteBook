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
echo '$name'

# 
```
