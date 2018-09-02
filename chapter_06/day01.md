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