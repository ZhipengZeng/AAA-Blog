---
layout: default
title: Note of Unix
---
##A Note of Unix Problems I Met (keep updating)	
1.	`>` and `>>`	

	>	> writes to a file, overwriting any existing contents.	 
	>	>> appends to a file.		
2.	Add a number of user in Unix 	

	>	#!/bin/bash		
	>	i=1 	
	>	while [ $i -le 100 ]	
	>	do 	
	>	USERNAME=user${i} 	
	>	id ${USERNAME} &> /dev/null 	
	>	if [ $? -eq “0” ]; then 	
	>	echo “${USERNAME} is exists” 	
	>	i=$(($i+1)) 	
	>	else 	
	>	useradd ${USERNAME} 	
	>	echo “${USERNAME}” |passwd –stdin ${USERNAME} > /dev/null 	
	>	echo “${USERNAME} add commplete…” 	
	>	i=$(($i+1)) 	
	>	fi 	
	>	done 	
	>	exit 0				
