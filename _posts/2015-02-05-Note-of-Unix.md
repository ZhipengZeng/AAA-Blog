---
layout: post
title: Note of Unix 
category: Programming
tag: [ Unix, Note ]
---  

## A Note of Unix Problems I Met (keep updating)	  
1. (2015/02/05) `>` and `>>`
    *	`>` writes to a file, overwriting any existing contents.	 
    *	`>>` appends to a file.
2. (2015/02/05) Here is a shell script for creating a amount of users from imported file
{% highlight bash %}
#!/bin/bash  
if [ $# -ne 1 ]  
then    
    echo USAGE: $0 filename.csv
    exit 1
fi  
grep -i "^students" /etc/group
if [ $? -ne 0 ]
then
    groupadd students
fi
while read line  
do  
    FIRST=`echo $line | cut -d '"' -f2 | cut -d ',' -f2`  
    LAST=`echo $line | cut -d '"' -f2 | cut -d ',' -f1`  
    NAME="$FIRST $LAST"  
    USERID=`echo $line | cut -d ',' -f3`  
    HOMEDIR="/home/${USERID}"  
    GROUPNAME=students  
    STARTUPSHELL=/bin/bash  
    useradd -g ${GROUPNAME} -p `(echo ${USERID}; sleep 1; echo ${USERID}) | grub-md5-crypt 2> /dev/null | tail -1` -d ${HOMEDIR} -m -s ${STARTUPSHELL} -c "${NAME}" ${USERID}  
    echo $?
done < $1  
exit 0
{% endhighlight %}