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