### 网络安全: 防火墙 ###
防火墙（Firewall），也称防护墙，是由Check Point创立者Gil Shwed于1993年发明并引入国际互联网。

防火墙是位于内部网和外部网之间的屏障，它按照系统管理员预先定义好的规则来控制数据包的进出。

防火墙是系统的第一道防线，其作用是防止非法用户的进入。

查询防火墙状态

	systemctl status firewalld.service
	firewall-cmd --state

重启防火墙操作

	systemctl restart firewalld.service
	service firewalld restart

通过服务名称放行Apache服务

	查询public区的防火墙信息
	firewall-cmd --list-all --zone=public

	临时放行Apache服务到public区，立即生效，重启失效
	firewall-cmd --add-service http --zone=public
	
	永久放行Apache服务到public区，重启读取配置生效
	firewall-cmd --permanent --add-service http --zone=public
	
	以 root 身份输入以下命令，重新加载防火墙，并不中断用户连接，即不丢失状态信息
	firewall-cmd --reload

	临时从防火墙的public区移除Apache放行，立即生效，重启失效
	firewall-cmd --remove-service http --zone=public
	
	永久从防火墙的public区移除Apache放行，重启读取配置生效
	firewall-cmd --permanent --remove-service http --zone=public

通过端口的方式放行httpd服务

	查询public区的防火墙信息
	firewall-cmd --list-all --zone=public

	临时放行Apache服务到public区，立即生效，重启失效
	firewall-cmd --add-port=80/tcp --zone=public

	永久放行Apache服务到public区，重启读取配置生效
	firewall-cmd --permanent --add-port=80/tcp --zone=public

	以 root 身份输入以下命令，重新加载防火墙，并不中断用户连接，即不丢失状态信息
	firewall-cmd --reload

	临时从防火墙的public区移除Apache放行，立即生效，重启失效
	firewall-cmd --remove-port=80/tcp --zone=public
	
	永久从防火墙的public区移除Apache放行，重启读取配置生效
	firewall-cmd --permanent --remove-port=80/tcp --zone=public

配置完成防火墙规则后，需要重启防火墙服务，或重新加载防火墙配置，或重启服务器。