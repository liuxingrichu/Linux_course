### 网络安全: SELinux ###
SELinux(Security-Enhanced Linux) 是美国国家安全局（NSA）对于强制访问控制的实现，是 Linux历史上最杰出的新安全子系统。

NSA是在Linux社区的帮助下开发了一种访问控制体系，在这种访问控制体系的限制下，进程只能访问那些在他的任务中所需要文件。

SELinux 默认安装在 Fedora 和 Red Hat Enterprise Linux 上，也可以作为其他发行版上容易安装的包得到。

查询SELinux状态

	getenforce
	sestatus		//SELinux status参数为enabled即为开启状态
	sestatus -v

临时设置

	设置SELinux 成为permissive模式（临时关闭，重启失效）
	setenforce 0
	
	设置SELinux 成为enforcing模式（临时开启，重启失效）
	setenforce 1 

永久关闭，重启生效
	
	vim /etc/selinux/config
	
		#SELINUX=enforcing
		SELINUX=disabled