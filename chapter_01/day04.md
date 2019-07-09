### Win10系统安装Ubuntu系统 ###

注意：该安装方法需要在Windows10正版系统上，进行安装，其安装过程类似安装其他应用软件，例如QQ。

1. 按键盘上的【win】键（带微软旗帜标志），输入“功能”，打开【启动或关闭Windows功能】设置界面，选择底下的【适用于Linux的Windows子系统】，确认。
2. 按下键盘的【win】键（那个微软的旗子标志），直接输入“开发者”，打开【开发者选项设置】，选择【开发人员模式】。
3. 重启系统。
4. 按一下【win】键，找到【微软应用商店】，也叫Microsoft store。
5. 打开之后，在搜索框输入【ubuntu】，选择第一个那个安装人多的，点击安装，等待下载完成及安装，约5分钟左右。
6. 按一下【win】键，书写Ubuntu，选择Ubuntu应用，启动后需要安装约5分钟左右，在这个过程中，需要输入用户名和密码，但不能输入root用户，系统已内置root，例如可创建fsp用户。
7. 系统登录，输入用户名和密码，即可进行系统。
8. 关闭：直接关闭，或logout或exit即可。

### Win10系统下使用Ubuntu系统 ###

1. 系统字体调整：右键-》属性-》字体
2. Linux系统与Windows文件共享
	1. cd /mnt/d	进行Windows系统D盘
	2. mkdir /mnt/d/day0709		在D盘下创建day0709目录
3. cd !$  回到上一个目录
4. 系统安装软件
	1. sudo apt-get update
	2. sudo apt-get install mariadb-server