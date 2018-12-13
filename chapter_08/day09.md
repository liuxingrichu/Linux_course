### 函数 ###
函数是shell脚本中，自定义的一系列执行命令。

使用还是个最大好处是可避免出现大量重复代码，同时增强了脚本的可读性。

	函数定义方法：

		function FUNCTION_NAME(){
			command1
			command2
			...
		}

	
	举例：
	
		#!/bin/bash
		# demo for function
		
		FILE=/etc/passwd
		
		function print_line(){
			while read line
			do
				echo "$line"
			done < $FILE
		}
		
		echo " call function print_line "
		print_line