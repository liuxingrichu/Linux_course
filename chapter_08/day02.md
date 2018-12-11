### HelloWorld脚本程序：注释 运行 环境配置文件 ###

编写shell脚本程序

	vim first.sh
	
		#!/bin/bash					//脚本的第一行
		#This line is a comment.	//#表示注释
		echo "Hello World!"			//输出

注释

	shell脚本程序的注释为#。

运行shell脚本程序

	1. sh 脚本程序 或 bash 脚本程序
	2. 赋予执行权限，./脚本程序
	3. 赋予执行权限，脚本程序绝对路径
	4. bash < 脚本程序 或 sh < 脚本程序

环境配置文件

	全局设置文件：/etc/profile	/etc/bashrc
	用户设置文件:~/.bash_profile	~/.bashrc
	读取顺序
		1. /etc/profile
		2. ~/.bashrc
		3. /etc/bashrc
		4. ~/.bash_profile