### uname命令 ###
- 查询系统系统：uname
	- 查看内核信息：uname -r
	- 获取帮助信息：
		- uname --help
		- man uname
	- 查看系统架构：uname -m
	- 查看内核名：
		- uname 
		- uname -s
	- 查看全部信息：uname -a


			$ uname -a
			Linux bogon 3.10.0-862.el7.x86_64 #1 SMP Fri Apr 20 16:44:24 UTC 2018 x86_64 x86_64 x86_64 GNU/Linux
				
				Linux	内核名
				bogon	主机名
				3.10.0-862.el7.x86_64	内核版本
				#1 SMP Fri Apr 20 16:44:24 UTC 2018	内核编译日期
				x86_64	操作系统版本
				x86_64	处理器类型
				x86_64	硬件平台
				GNU/Linux	操作系统




