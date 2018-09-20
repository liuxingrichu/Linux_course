### sudo ###
1. 语法：sudo   命令 
2. 功能： sudo可让用户以其他的身份来执行指定的命令，预设的身份为root。在/etc/sudoers中，设置了可执行sudo命令的用户。若其未经授权的用户企图使用sudo，则会发出警告的邮件给管理员。

sudo的目的：为非根用户授予根用户的权限

配置文件：/etc/sudoers

visudo命令，编辑修改/etc/sudoers配置文件


	授权admin用户，添加用户权限
	授权admin用户，shutdown命令立刻关机

	## Allow root to run any commands anywhere
	root    ALL=(ALL)       ALL
	admin   ALL=(root)      /usr/sbin/useradd
	
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


### visudo命令，提示busy ###
1. 现象
	1. visudo: /etc/sudoers busy, try again later
2. 处理方法
	1. 查询visudo进程
	2. 杀进程vusudo
	3. 删除sudoer的缓存文件，若删除后，还生成，需要重启。	




