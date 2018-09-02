### apache服务器 ###
1. 镜像挂载
2. 安装
	1. yum install httpd
3. 服务启动
	1. # service httpd start
4. 查询
	1. # service httpd status
	2. 端口信息：# netstat -antp
5. 测试
	1. 关闭防火墙：# systemctl stop firewalld.service
	2. 客户端访问：http://10.103.79.7/

### mysql数据库 ###
1. 镜像挂载
2. 安装
	1. # yum -y install mysql*
3. 查询
	1. # rpm -qa | grep mysql
4. 卸载
	1. # yum -y remove mysql*
5. 登陆

		# mysql -uroot -p123456
		提示错误：ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/lib/mysql/mysql.sock' (2)
		原因定位：镜像中没有MySQL数据库，有mariadb数据库。
		解决方法：
			1. 安装mariadb数据库
			2. 源码安装MySQL数据库


# tar -zxvf mysql-5.6.26.tar.gz