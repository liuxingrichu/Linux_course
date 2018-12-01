### 常用命令：ping ifconfig ifup ifdown route netstat traceroute wget chkconfig ###
1. ping
	1. 语法：ping [参数] IP地址
	2. 功能：检查网络是否畅通或网络连接速度。

			参数：
				-c	在发送指定数目的包后，停止。
			
			说明： Linux中，ping不会自动终止，需要按“Ctrl + c”终止或用参数“-c”指定要求完成的回应次数。
			
			举例：
				ping 192.168.1.110
				ping -c 3 192.168.1.111


2. ifconfig
	1. 语法：ifconfig [网络接口名] [address] [up|down]
	2. 功能：可用来查看、配置、启动或禁用网络接口。
	
			说明：
				lo为本地环回接口，IP地址为127.0.0.1，子网掩码8位，表示本机。
				inet表示IPv4的网卡IP，netmask表示子网掩码，broadcast表示广播地址。
			
			举例：
				ifconfig
				ifconfig ens33
				临时配置网络信息，其立即生效，重启失效
				ifconfig ens33 192.168.1.110/24						
				ifconfig ens33 192.168.1.110 netmask 255.255.255.0	
				service network restart
				ifconfig ens33 down
				ifconfig ens33 up

3. ifup
	1. 语法：ifup 网络接口名
	2. 功能：开启对应网络接口。
	3. 举例： ifup ens33

4. ifdown
	1. 语法：ifdown 网络接口名
	2. 功能：禁用对应网络接口。
	3. 举例：ifdown ens33

5. route
	1. 语法：route [参数]
	2. 功能：可查看或编辑IP路由表。

			举例：
				route
				route -n
				route add default gw 192.168.1.1

6. traceroute
	1. 语法：traceroute 域名或IP
	2. 功能：用于显示从本机到目标机的数据包所经过的路由。
	3. 举例：
		1. traceroute wwww.baidu.com
		2. traceroute 192.168.1.109

7. netstat
	1. 语法：netstat [参数]
	2. 功能：显示网络连接、路由表或接口状态

			参数：
				-a	显示所有连接中的socket
				-n	直接使用IP地址
				-p	显示正在使用socket的程序名称
				-r	显示路由表
			
			举例：
				netstat -anp | grep http
				netstat -r

8. wget
	1. 语法：wget [参数] [目标软件地址]
	2. 功能：类似Windows中的下载工具，用于下载某个文件。

			参数：
				-c	断点下载
			
			举例：
				wget http://nginx.org/download/nginx-1.14.1.tar.gz
				wget -c http://nginx.org/download/nginx-1.14.1.tar.gz

9. chkconfig
	1. 语法：chkconfig [参数] [服务名] [on|off]
	2. 功能：指定服务在系统开机是否自启动，即开机后，服务是开启还是关闭。

			参数：
				--add	添加服务
				--del 	删除服务
				--level	等级
			
			举例
				chkconfig
				chkconfig --add nginx
				chkconfig --del nginx
				chkconfig nginx off
				chkconfig --level 3 nginx on

