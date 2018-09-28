### 用户管理之课堂练习 ###
1. 在Linux下新建用户 user01，并设置密码为123，查看文件/etc/passwd,/etc/shadow以及/home目录下文件变化。
2. 修改user01用户名为user1。
3. 锁定该用户，查看/etc/shadow文件变化。并用user1用户登录系统，然后解除锁定，再用user1用户登录系统看是否能正常登录。
4. 删除该用户。


		1. 在Linux下新建用户 user01，并设置密码为123，查看文件/etc/passwd,/etc/shadow以及/home目录下文件变化。
		
		# useradd user01
		# passwd user01
		tail -n 3 /etc/passwd
		# tail -n 3 /etc/shadow
		cd /home
		ls
		
		2. 修改user01用户名为user1。
		
		# usermod -l user1 user01
		3. 锁定该用户，查看/etc/shadow文件变化。并用user1用户登录系统，然后解除锁定，再用user1用户登录系统看是否能正常登录。
		
		# usermod -L user1
		# tail -n 3 /etc/shadow
		# logout
		# usermod -U user1
		# cat /etc/shadow
		
		4. 删除该用户。
		
		# userdel user1