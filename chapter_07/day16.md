### 网络配置之动态IP、静态IP的最小化配置 ###
- 环境描述
	- Windows 7台式电脑，无外网，有局域网其默认分配IP为172.18.86.11-50/24。

- 动态IP配置（NAT模式）
	- 需要在NAT模式下进行操作，因为此时桥接模式获取不到IP地址，其原因是交换机DHCP服务无法分配网络地址。


	最小化配置（命令方式能正常管理网络服务，与宿主机正常通信）

		vim /etc/sysconfig/network-scripts/ifcfg-ens33
		
			BOOTPROTO="dhcp"
			DEVICE="ens33"

- 静态IP配置（桥接模式）
	- 需要在桥接模式下进行操作，因为NAT模式下，配置的静态IP，与宿主机无法互通。


	最小化配置（命令方式能正常管理网络服务，与宿主机正常通信）
	
		vim /etc/sysconfig/network-scripts/ifcfg-ens33
		
			BOOTPROTO="static"
			DEVICE="ens33"
			IPADDR="172.18.86.120"			
	
			或者

			BOOTPROTO=none
			DEVICE=ens33
			IPADDR=172.18.86.120

