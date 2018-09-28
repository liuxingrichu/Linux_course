### 组管理之课堂练习 ###
- 课堂练习1
	1. 查看当前在线的用户，查询有没有要创建的用户user1;
	2. 创建用户user1;
	3. 创建用户组 group1，并查看文件/etc/group,/etc/gshadow文件变化;
	4. 管理组成员，将用户user1加入到组里group1;
	5. 删除用户及用户组。
	
	
			1.1 查看当前在线的用户
			w
			who
			users
			
			1.2 查询有没有要创建的用户user1
			id users
			cat /etc/passwd | grep user1
			# cat /etc/shadow | grep user1

			2. 创建用户user1;
			
			# useradd user1
			3. 创建用户组 group1，并查看文件/etc/group,/etc/gshadow文件变化;
			
			# groupadd group1

			cat /etc/group | grep group1
			cat /etc/group | more
			cat /etc/group | less
			cat /etc/group 
			tail /etc/group
			tail -n 3 /etc/group
			vim /etc/group
			head /etc/group
		
			
			
			4. 管理组成员，将用户user1加入到组里group1;
			
			# gpasswd -a user1 group1
			
			5. 删除用户及用户组。
			
			# userdel user1
			# groupdel group1
			# gpasswd -d user1 group1
- 课堂练习2
	1. 新建一个账户为test的用户并设置密码
	2. 新建一个组名为zte的组
	3. 把test用户加入到zte组中
	4. 为zte组开放shutdown -h now权限。
	5. 在用户test下使用shutdown -h now命令

			1. 新建一个账户为test的用户并设置密码
			
			#useradd test
			#passwd test
			2. 新建一个组名为zte的组
			
			#groupadd zte
			3. 把test用户加入到zte组中
			
			#gpasswd -a test zte
			4. 为zte组开放shutdown -h now权限。
			
			# visudo
			
				## Allows members of the users group to shutdown this system
				# %users  localhost=/sbin/shutdown -h now
				%zte  localhost=/sbin/shutdown -h now
			
			5. 在用户test下使用shutdown -h now命令
			
			# su test
			$ sudo shutdown -h now

