### ping通8.8.8.8，不通百度 ###

- 问题现象

		[root@localhost ~]# ping www.baidu.com
		ping: www.baidu.com: 未知的名称或服务
		[root@localhost ~]# ping -c 3 8.8.8.8
		PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
		64 bytes from 8.8.8.8: icmp_seq=1 ttl=128 time=42.5 ms
		64 bytes from 8.8.8.8: icmp_seq=2 ttl=128 time=42.7 ms
		64 bytes from 8.8.8.8: icmp_seq=3 ttl=128 time=41.9 ms
		
		--- 8.8.8.8 ping statistics ---
		3 packets transmitted, 3 received, 0% packet loss, time 2005ms
		rtt min/avg/max/mdev = 41.976/42.432/42.736/0.369 ms
		[root@localhost ~]#
- 定位
	- dns的问题，需要配置dns服务器。
- 解决方法：

		vi /etc/resolv.conf
			# Generated by NetworkManager
			nameserver 8.8.8.8
