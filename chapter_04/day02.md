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

重复之美

	现象描述：
	
		完成上述操作后，再进行用户user01用户添加时，提示一下信息：
		
			useradd: group user01 exists - if you want to add this user to that group, use -g.
		
		id查询，其未添加用户user01
	
	问题定位：
	
	
		查询用户基本信息，未发现用户user01信息
		
			tail -n 3 /etc/passwd
		
		查询组基本信息，发现有组user01信息
		
			tail -n 3 /etc/group
		
		useradd命令，在添加用户的同时，创建了一个与用户同名的用户基本组，因为user01的基本组已存在，故导致无法使用"useradd user01"命令创建用户，得到上面的提示信息。
	
	解决方法：
	
		方法一：消除历史干扰
		
			groupdel user01
		
		方法二：按照信息提示，手动指定用户组
	
			useradd user01 -g user01