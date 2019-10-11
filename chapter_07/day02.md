### 网络配置：dhcp和static ###
系统默认配置

	vim /etc/sysconfig/network-scripts/ifcfg-ens33
	
		TYPE="Ethernet"			//设备连接类型，此处为以太网
		PROXY_METHOD="none"		
		BROWSER_ONLY="no"
		BOOTPROTO="dhcp"		//取得IP的方式，dhcp或none或static
		DEFROUTE="yes"			//是否为默认路由
		IPV4_FAILURE_FATAL="no"
		IPV6INIT="yes"
		IPV6_AUTOCONF="yes"
		IPV6_DEFROUTE="yes"
		IPV6_FAILURE_FATAL="no"
		IPV6_ADDR_GEN_MODE="stable-privacy"
		NAME="ens33"			//设备名，此处对应网络接口为ens33
		UUID="e1e2fab8-4134-4da4-9de7-153bf8f13c01"
		DEVICE="ens33"			//网卡名称，必须与文件名部分对应
		ONBOOT="yes"			//系统启动时，是否此网络接口启动

配置动态IP

	vim /etc/sysconfig/network-scripts/ifcfg-ens33
	
		BOOTPROTO="dhcp"
		DEVICE="ens33"
		ONBOOT="yes"

配置静态IP

	vim /etc/sysconfig/network-scripts/ifcfg-ens33
	
		BOOTPROTO="static"
		DEVICE="ens33"
		ONBOOT="yes"
		IPADDR="192.168.1.108"			//IP
		NETMASK="255.255.255.0"			//子网掩码
		GATEWAY="192.168.1.1"			//默认路由
	
		或者
		BOOTPROTO=none
		DEVICE=ens33
		ONBOOT=yes
		IPADDR=192.168.1.108
		NETMASK=255.255.255.0
		GATEWAY=192.168.1.1

网络重启

	service network restart
	systemctl restart network
	systemctl restart network.service
	/etc/init.d/network restart

互联网网络测试

	ping www.baidu.com
	ping 8.8.8.8

- 校园网特殊情况说明
	- 校园网中，一般需要认证通过的用户，才能连接互联网。
	- 实验室和办公室zls无线网络，通过特殊设置，无需认证上网。
	- 2.4G和5.8G无线网络，需要认证上网。Linux系统，也是一个设备，同样需要认证，才能上网。
	- 出现以下现象，原因为上面的阐述：
		- 连接zls无线网络，Linux获取到IP, 192.168.1.x/24, 能通过互联网网络测试。
		- 在实验室有线网络情况下，Linux获取到IP, 172.18.8.x/24, 能通过互联网网络测试。
		- 在2.4G或5.8G无线网络下，Linux获取到IP，不能通过互联网网络测试。
		- 在连接手机无线热点情况下，Linux获取到IP，能通过互联网网络测试。


- 自动获取IP
	- dhclient