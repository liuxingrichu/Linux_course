### maria数据库 ###
1. 介绍
	1. 关系型数据库
	2. 免费开源的数据库
	3. 创建人：mysql之父（Michael Widenius）
	4. 兼容mysql
	2. MariaDB数据库管理系统是MySQL的一个分支，主要由开源社区在维护，采用GPL授权许可 MariaDB的目的是完全兼容MySQL，包括API和命令行，使之能轻松成为MySQL的代替品。在存储引擎方面，使用XtraDB（英语：XtraDB）来代替MySQL的InnoDB。 MariaDB由MySQL的创始人Michael Widenius（英语：Michael Widenius）主导开发，他早前曾以10亿美元的价格，将自己创建的公司MySQL AB卖给了SUN，此后，随着SUN被甲骨文收购，MySQL的所有权也落入Oracle的手中。MariaDB名称来自Michael Widenius的女儿Maria的名字。
2. 安装
	1. # yum install mariadb mariadb-server
	2. # rpm -qa | grep mariadb
3. 配置
	1. 设置开机启动
		1. # systemctl start mariadb
		2. # systemctl status mariadb
	2. MariaDB的相关简单配置


			首先是设置密码，会提示先输入密码
			
			Enter current password for root (enter for none):<–初次运行直接回车
			
			设置密码
			
			Set root password? [Y/n] <– 是否设置root用户密码，输入y并回车或直接回车
			New password: <– 设置root用户的密码
			Re-enter new password: <– 再输入一次你设置的密码
			
			其他配置
			
			Remove anonymous users? [Y/n] <– 是否删除匿名用户，回车
			
			Disallow root login remotely? [Y/n] <–是否禁止root远程登录,回车,
			
			Remove test database and access to it? [Y/n] <– 是否删除test数据库，回车
			
			Reload privilege tables now? [Y/n] <– 是否重新加载权限表，回车
			
			初始化MariaDB完成

			# mysql_secure_installation
			
				NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
				      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!
				
				In order to log into MariaDB to secure it, we'll need the current
				password for the root user.  If you've just installed MariaDB, and
				you haven't set the root password yet, the password will be blank,
				so you should just press enter here.
				
				Enter current password for root (enter for none):
				OK, successfully used password, moving on...
				
				Setting the root password ensures that nobody can log into the MariaDB
				root user without the proper authorisation.
				
				Set root password? [Y/n] y
				New password:
				Re-enter new password:
				Password updated successfully!
				Reloading privilege tables..
				 ... Success!
				
				
				By default, a MariaDB installation has an anonymous user, allowing anyone
				to log into MariaDB without having to have a user account created for
				them.  This is intended only for testing, and to make the installation
				go a bit smoother.  You should remove them before moving into a
				production environment.
				
				Remove anonymous users? [Y/n]
				 ... Success!
				
				Normally, root should only be allowed to connect from 'localhost'.  This
				ensures that someone cannot guess at the root password from the network.
				
				Disallow root login remotely? [Y/n] n
				 ... skipping.
				
				By default, MariaDB comes with a database named 'test' that anyone can
				access.  This is also intended only for testing, and should be removed
				before moving into a production environment.
				
				Remove test database and access to it? [Y/n] n
				 ... skipping.
				
				Reloading the privilege tables will ensure that all changes made so far
				will take effect immediately.
				
				Reload privilege tables now? [Y/n]
				 ... Success!
				
				Cleaning up...
				
				All done!  If you've completed all of the above steps, your MariaDB
				installation should now be secure.
				
				Thanks for using MariaDB!

	3. 测试登录
		1. # mysql -uroot -p123db
		2. 查询端口号
			1. # netstat -anp | grep 3306
4. 使用
	1. show databases;
	2. use mysql;
	3. show tables;
	4. select * from user;
	5. show index from user;
	6. desc user;
	7. exit

[maria数据库官网](https://downloads.mariadb.org/)

[参与资料1](https://www.cnblogs.com/jpfss/p/6568976.html)

[参与资料2](https://github.com/liuxingrichu/advanced-network-program/tree/master/Mysql) 