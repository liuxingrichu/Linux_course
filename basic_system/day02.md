### 最小化Linux系统配置 ###
1. 更新系统yum源
	- yum clean all
	- yum update

2. 安装vim编辑器
	- yum install vim

3. 安装at命令
	- yum install at

4. 安装pstree命令
	- yum install psmisc

5. VMware挂载ISO文件
	1. 虚拟机-》可移动设备-》CD/DVD-》设置-》使用ISO映像文件
	2. 虚拟机-》可移动设备-》CD/DVD-》连接

6. 系统开机自动挂载ISO文件镜像


		mkdir /mnt/cdrom
	
		vim /etc/rc.local
			mount /dev/cdrom /mnt/cdrom
	
		ls -al /etc/rc.d/rc.local
		chmod +x /etc/rc.d/rc.local

7. 用户级清除历史记录
	
		cd
		echo > .bash_history
		history -cw

8. 获取帮助信息
	- help history

9. 用户级自定制history信息显示格式

		cd 
		vim /root/.bashrc
			export HISTTIMEFORMAT="%F %T `whoami` "

10. 配置vim编辑器
	1. 全局生效
	
			# vim /etc/vimrc
			
			在文件最后添加，以下语句
				set nu         // 设置显示行号
			   	set showmode   //设置在命令行界面最下面显示当前模式等。
			   	set ruler     // 在右下角显示光标所在的行数等信息
			   	set autoindent   // 设置每次单击Enter键后，光标移动到下一行时与上一行的起始字符对齐
			   	syntax on    // 即设置语法检测，当编辑C或者Shell脚本时，关键字会用特殊颜色显示
	
	2. 当前用户生效
		- 在用户登录的 ~ 目录下创建一个 .vimrc文件，在其中进行自己习惯的编程环境的设置，这样当别的用户使用实并不互相影响。

11. 通过visudo命令，配置admin用户部分权限

		授权admin用户，添加用户权限
		授权admin用户，删除用户权限
		授权admin用户，无密码方式添加组权限
		授权admin用户，无密码方式删除组权限
		授权admin用户，shutdown命令立刻关机
	
		## Allow root to run any commands anywhere
		root    ALL=(ALL)       ALL
		admin   ALL=(root)      /usr/sbin/useradd, /usr/sbin/userdel
		admin   ALL=(root)      NOPASSWD:/usr/sbin/groupadd, /usr/sbin/groupdel
		
		## Allows members of the 'sys' group to run networking, software,
		## service management apps and more.
		# %sys ALL = NETWORKING, SOFTWARE, SERVICES, STORAGE, DELEGATING, PROCESSES, LOCATE, DRIVERS
		
		## Allows people in group wheel to run all commands
		%wheel  ALL=(ALL)       ALL
		
		## Same thing without a password
		# %wheel        ALL=(ALL)       NOPASSWD: ALL
		
		## Allows members of the users group to mount and unmount the
		## cdrom as root
		# %users  ALL=/sbin/mount /mnt/cdrom, /sbin/umount /mnt/cdrom
		
		## Allows members of the users group to shutdown this system
		# %users  localhost=/sbin/shutdown -h now
		%admin  localhost=/sbin/shutdown -h now

12. traceroute命令
	- yum install traceroute

13. wget命令
	- yum install wget

14. 服务篇
	- yum install vsftpd
	- yum install httpd
	- yum install mariadb mariadb-server

15. 更换默认语言，设置为中文简体
	1. 安装系统时，选择安装中文
	2. 永久更改系统默认语言

			vim /etc/locale.conf
			
				将
					LANG="en_US.UTF-8"
				修改为
					LANG="zh_CN.UTF-8"