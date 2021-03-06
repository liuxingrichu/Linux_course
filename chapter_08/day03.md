### 变量 ###
变量

	变量就是其值可以变化的量。
	
	从变量的实质来说，变量名是指向一片用于存储数据的内存空间。
	
	shell变量是一种弱类型的变量，也就是说在声明变量时，不需要指定其变量类型。
	
	局部变量是指在某个shell中生效的变量。

	环境变量，也称全局变量，变量全局有效。
	export内建命令，将其导出为环境变量。
	
	echo $HOSTNAME	//展示主机名
	echo $LANG		//查看当前系统的语言环境		
	echo $PWD		//查看记录当前目录
	echo $PATH		//命令的搜索路径

变量命名

	变量必须以字母或下划线开头，后面可以跟数字、字母和下划线，变量长度没有限制，不建议太长。
	变量区分大小写。
	不能使用预设变量名，例如PATH
	不能使用关键字，例如if，for

变量赋值

	定义变量：变量名=变量值
	
		注意
		1. 变量名和变量值之间用等号连接，之间不能有任何空格。
		2. 当变量中有空格时，必须用引号括起来。
		3. 变量先声明再使用，即定义在前，使用在后。
	
		举例：
			name=john
			name="Xiaoming Li"



变量取值：在变量名前加上$符合即可，严谨一点的写法是${}。

	注意：若变量值引用的是其它变量，则必须用双引号。单引号会不解析特殊字符$。 

	举例：
		echo $name
		echo "${name}hello, nice to meet you." 

取消变量：将变量从内存中释放。

	unset 变量名

特殊变量

	位置参数

		$0		//脚本本身
		$1		//第一个参数
		$2		//第二个参数
		...
		${10}	//第10个参数
		$#		//脚本参数的个数总和
		$@		//脚本的所有参数
		$*		//脚本的所有参数
	
	举例：
	
		#!/bin/bash
		# test positional parameter
		echo "\$0       ===> $0"
		echo "\$1       ===> $1"
		echo "\$2       ===> $2"
		echo "\$10      ===> $10"
		echo "\${10}    ===> ${10}"
		echo "\$#       ===> $#"
		echo "\$@       ===> $@"
		echo "\$*       ===> $*"

脚本或命令返回值：$?

	Linux中，规定正常退出的命令和脚本，应该以零作为其返回值，任何非零的返回值都表示命令未正确退出或未正常执行。

	$?永远是上一个命令的返回值。