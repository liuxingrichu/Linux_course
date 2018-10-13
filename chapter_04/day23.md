### 进程管理（下）之练习 ###
1. 每分钟向终端tty1，输出“hello, tty1”。
2. 查询全部系统信息
3. 查询主机名，并修改主机名修改为test。
4. 查询系统内存信息。
5. 查询系统当前运行级别，并将其切换到多用户的命令行界面等级。
6. 查询系统时间，并实现系统时间倒转10年。

		1. 每分钟向终端tty1，输出“hello, tty1”。
		
			# crontab -e
			* * * * * echo "hello, tty1" > /dev/tty1
		2. 查询全部系统信息
		
			$ uname -a
		3. 查询主机名，并将主机名修改为test。
		
			$ hostname
			$ uname 
			$ uname -s
			
			$ hostname test
			或
			$ hostnamectl set-hostname test
			或
			$ vim /etc/hostname
		4. 查询系统内存信息。
		
			free
		5. 查询系统当前运行级别，并将其切换到多用户的命令行界面等级。
		
			# runlevel
			# init 3
		6. 查询系统时间，并实现时光倒转10年。
		
			# date
			# date -s "20081013 20:30"