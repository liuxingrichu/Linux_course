1. 添加组密码，用户登录时，需要输入密码，如何实现？
3. 文件/etc/shadow权限全部为-，root用户可以读，为什么？
	1. root用户为超级用户
	2. 写出全-是建议root用户也不要修改
5. 用户的主属组，是什么含义？
	1. 用户创建的第一分组
6. 如何收回普通用户的权限？
7. /home目录下的total，为什么为0？
	1. 现在又正常显示内容了！！！
8. 权限修改reboot命令，为什么不生效？
9. ps -l中F的0值是什么含义？
10. ps -l执行后显示的进程信息中F的值，有的是0，有的是4，什么原因？
11. 如何查询at命令下发的相关进程是什么？
12. ntp实现网络时间同步异常。
13. 文件系统从ext2文件系统切换到xfs或btrfs系统需要强制，而从xfs系统切换到ext2/3/4，却不需要强制？
14. 命令行终端提示“blk_update_request: I/O error, dev fd0, sector 0”错误。
15. 硬链接和软链接，区分的必要性，两者的主要用途？
16. 通过dd命令，例如dd if=/dev/sda of=/home/test/centos7_64_1019.iso，生成的iso文件大小超过15G，是为什么？
17. 通过“dd if=/dev/sda of=/dev/sda”，磁盘可以正常使用？但“dd if=tmp.txt of=test.txt”命令，其文件内容没有了？
18. kill强杀进程1、2、3等特殊进程，无法杀死？
19. 通过ifconfig手动配置，Linux与Windows系统无法正常通信？
20. 连接2.4G网络，有时Linux系统的IP地址不见了，过一会又有了，网络不稳定？
21. 连接zls网络，电脑IP地址会出现不定时变化，是什么原因？
22. tmp目录，显示的文件详细信息不同
	1. cd /;ll 查看到的tmp目录
	2. ll /tmp或ll /tmp/查看的内容
	3. ll -d /tmp或ll /tmp/

23. 192.168.1.106/24可以向172.18.8.109传输文件（Linux系统），而Windows系统之间不可以访问共享。

24. https访问Apache服务器，使用443端口
25. 域名方式访问www服务器
26. 防火墙规则临时配置及永久配置
	1. firewall
	2. iptables
27. ftp方式配置yum源
28. nfs测试是否可以配置yum源
29. nginx配置yum源
30. SELinux规则