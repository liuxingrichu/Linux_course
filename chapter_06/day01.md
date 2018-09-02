### 镜像挂卸载 ###
1. VMware的虚拟机-》可移动设备-》CD/DVD-》设置-》使用ISO映像文件-》浏览选择文件-》确定
2. VMware的虚拟机-》可移动设备-》CD/DVD-》连接
3. 确认连接状态：VMware的虚拟机-》可移动设备-》CD/DVD-》断开连接
4. 用root账号登录Linux系统，执行以下命令

		cd /mnt
		mkdir cdrom
		mount /dev/cdrom /mnt/cdrom/
		cd cdrom
		ls
		umount -v /mnt/cdrom

### 安装ifconfig命令工具包 ###
	# ifconfig
	# mount /dev/cdrom /mnt/cdrom/
	# cd cdrom/Packages
	# ls | grep net-tool*
	# rpm -iv net-tools-2.0-0.22.20131004git.el7.x86_64.rpm
	# ifconfig

### 配置yum本地源 ###
	# mount | grep /dev/sr0 	//确定镜像挂载磁盘
	# cd /etc/yum.repos.d/
	# mkdir bak
	# mv * bak/
	# vi 1.repo
	
		[1]							//自定义
		name=1						//自定义
		baseurl=file:///mnt/cdrom/	//实际路径
		gpgcheck=0					//必须是0，这样就不会检查
		enabled=1					//必须是1，这样配置文件才生效
	# yum -y install vim* 			//测试本地yum配置：安装vim
	# vimtutor
	
