### 循环 ###
for循环

	for VARIABLE in LIST
	do
		command
	done
	
	类C的for循环
	for ((expression1; expression2; expression3))
	do
		command
	done
	
		#!/bin/bash
		sum=0
		for VAR in `seq 1 100`
		do
			let "sum+=VAR"
		done
		echo "Total: $sum"
		
		#!/bin/bash
		sum=0
		for ((i=1;i<=100;i++))
		do
			let "sum+=$i"
		done
		echo "Total: $sum"

while循环

	while expression
	do
		command
	done
	
	while true
	do
		comand
	done

		#!/bin/bash
		# The sum of odd numbers in 100.
		sum=0
		i=1
		j=1
		while [[ $i -le 100 ]]
		do
			let "j=i%2"
			if [[ $j -ne 0 ]]; then
				let "sum+=$i"
			fi
			let "i+=1"
		done
		echo "sum=$sum"


until循环

	until expression
	do
		command
	done

select循环

	select MENU in LIST
	do
		command
	done

break语句

	用于终止当前整个循环体。

continue语句

	用于结束当前循环，转而进入下一次循环。


嵌套循环：OK