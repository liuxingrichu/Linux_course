### 目录 ###
1. Linux概述
	1. [Linux系统介绍](chapter_01/day01.md)
	2. [Linux发展前景](chapter_01/day02.md)
	3. [Linux学习资源](chapter_01/day02.md)
	4. [Linux学习习惯](chapter_01/day02.md)
	5. [练习](chapter_01/day03.md)
2. 系统安装与基本配置
	1. [虚拟化、虚拟机软件介绍](chapter_02/day01.md)
	2. [硬盘、分区、硬盘分区](chapter_02/day02.md)
	3. [Linux系统启动流程1](chapter_02/day03.md)
	4. [Linux系统启动流程2](chapter_02/day04.md)
	5. [练习](chapter_02/day05.md)
	6. [文件系统](chapter_02/day06.md)
	7. [独立思考时间颗粒度](chapter_02/day07.md)
	8. [询问问题参考模板](chapter_02/day07.md)
	9. [VMware虚拟机加载镜像，无法正常查看和操作系统](chapter_02/day07.md)
	10. [虚拟机安装Linux系统黑屏](chapter_02/day07.md)
	11. [Linux系统安装流程](chapter_02/day08.md)
3. 系统用户接口和程序编辑器
	1. 系统用户接口
		1. [控制台和终端、shell](chapter_03/day01.md)
		2. [修改系统默认运行级别](chapter_03/day01.md)
		3. [配置用户开启自启动](chapter_03/day01.md)
		4. [根目录与家目录的区别](chapter_03/day01.md)
		5. [命令全称获取方式](chapter_03/day02.md)
		6. [常用命令清单1](chapter_03/day02.md)
		7. [命令缩写参考清单](chapter_03/day02.md)
		8. [通配符](chapter_03/day03.md)
		9. [重定向](chapter_03/day03.md)
		10. [管道](chapter_03/day03.md)
		11. [KDE和GNOME桌面环境](chapter_03/day03.md)
		12. [练习](day04.md)
		13. [ll命令的total](day08.md)
	2. 程序编辑器
		1. [配置vim编辑器](chapter_03/day05.md)
		2. [vim编辑器](chapter_03/day05.md)
		3. [vim编辑器之多文件](chapter_03/day07.md)
		4. [source /etc/vimrc报错](chapter_03/day05.md)
4. 系统管理
	1. 用户管理
		1. [用户管理](chapter_04/day01.md)
		2. [head命令](chapter_04/day01.md)
		3. [tail命令](chapter_04/day01.md)
		4. [创建用户的家目录内容来源](chapter_04/day01.md)
		5. [用户管理之课堂练习](chapter_04/day02.md)
		2. [组管理](chapter_04/day03.md)
		3. [身份切换](chapter_04/day04.md)
		3. [授权操作](chapter_04/day05.md)
		4. [visudo命令，提示busy](chapter_04/day05.md)
		5. [组管理之课堂练习](chapter_04/day06.md)
	2. 进程管理
		1. [程序与进程](chapter_04/day07.md)
		2. [特殊进程](chapter_04/day08.md)
		3. [监视进程：ps pstree](chapter_04/day09.md)
		4. [监视进程：top](chapter_04/day10.md)
		5. [进程管理（上）之练习题](chapter_04/day11.md)
		6. [搜索进程：pgrep pidof ps](chapter_04/day12.md)
		7. [控制进程: kill killall pkill xkill](chapter_04/day12.md)
		8. [进程优先级: nice renice](chapter_04/day13.md)
		9. [前后台进程: jobs fg bg kill](chapter_04/day14.md)
		10. [进程管理（中）之练习](chapter_04/day15.md)
		11. [例行任务管理: at、batch](chapter_04/day16.md)
		12. [例行任务管理: cron](chapter_04/day17.md)
		13. [不同来源的例行任务](chapter_04/day17.md)
		14. [uname命令](chapter_04/day18.md)
		15. [free命令](chapter_04/day19.md)
		16. [init命令](chapter_04/day20.md)
		17. [系统或硬件时间: date hwclock clock](chapter_04/day21.md)
		18. [其他命令:修改主机名、修改运行级别: hostname last man tzselect cal pwd reboot shutdown halt runlevel logout](chapter_04/day22.md)
		19. [进程管理（下）之练习](chapter_04/day23.md)
	3. 日志管理
5. 磁盘和文件管理
	1. 磁盘管理
		1. [文件系统](chapter_05/day001.md)
		2. [磁盘空间查询](chapter_05/day002.md)
		3. [磁盘分区](chapter_05/day003.md)
		4. [磁盘格式化](chapter_05/day004.md)
		5. [磁盘管理（上）之练习题](chapter_05/day005.md)
		6. [blk_update_request](chapter_05/day004.md)
		7. [文件系统与内存](chapter_05/day006.md)
		8. [磁盘挂卸载](chapter_05/day007.md)
		9. [开机启动挂载](chapter_05/day008.md)
		10. [dd命令](chapter_05/day009.md)
		11. [磁盘管理（下）之练习题](chapter_05/day010.md)
	2. 文件管理
		1. [目录和文件](chapter_05/day011.md)
		2. [绝对路径和相对路径](chapter_05/day011.md)
		3. [目录结构](chapter_05/day012.md)
		4. [目录的常用命令: ls](chapter_05/day013.md)
		5. [文件的常用命令: more less head tail cat wc file stat tac](chapter_05/day013.md)
		6. [文件管理（A）之练习题](chapter_05/day014.md)
		7. [文件和目录的增删改操作: mkdir touch cp scp mv rmdir rm](chapter_05/day015.md)
		8. [文件管理（B）之练习题](chapter_05/day016.md)
		9. [文件和目录的搜素: find locate which whereis](chapter_05/day017.md)
		10. [文件管理（C）之练习题](chapter_05/day018.md)
		11. [文件的追加与合并：echo cat uniq cut paste join tr](chapter_05/day019.md)
		12. [文件和目录的比较：diff](chapter_05/day020.md)
		13. [文件和目录的排序：sort](chapter_05/day021.md)
		14. [文件的链接: ln](chapter_05/day022.md)
		15. [字符处理与链接之练习](chapter_05/day023.md)
		16. [查看文件权限：ls -l](chapter_05/day024.md)
		17. [修改文件权限：chmod](chapter_05/day025.md)
		18. [修改文件归属：chown chgrp](chapter_05/day026.md)
		19. [默认权限：umask](chapter_05/day027.md)
		20. [文件权限之练习题](chapter_05/day028.md)
		21. [文件压缩与解压缩：gzip gunzip bzip2 bunzip2](chapter_05/day029.md)
		22. [查看压缩文件：zcat zless zmore bzcat bzless](chapter_05/day030.md)
		23. [打包命令：tar](chapter_05/day031.md)
		24. [文件压缩与解压缩之练习题](chapter_05/day032.md)
	3. 三剑客
		1. [三剑客之grep：grep .bashrc source](chapter_05/day033.md)
		2. [三剑客之sed：sed](chapter_05/day034.md)
		3. [三剑客之awk：awk](chapter_05/day035.md)
		4. [三剑客之练习题](chapter_05/day036.md)
6. 软件管理
	1. [rpm包管理](chapter_06/day001.md)
	2. [rpm包管理之练习题](chapter_06/day002.md)
	3. [yum包管理的基本原理](chapter_06/day003.md)
	4. [yum包管理的基本使用](chapter_06/day004.md)
	5. [基于ISO镜像构建yum本地源](chapter_06/day005.md)
	6. [yum包管理之练习题](chapter_06/day006.md)
	7. [基于HTTP构建yum网络源](chapter_06/day007.md)
	8. [C编译和运行](chapter_06/day008.md)
	9. [Java编译和运行](chapter_06/day009.md)
	3. 
	4. [中文显示、输入]()
	1. [rpm]()
	2. [yum]
	3. [自建本地yum源]()
	3. [自建网络yum源]()
	4. [源码安装: nginx]()
	5. [数据库安装: maria]()
	6. [程序编译与运行]()
	7. 
9. 网络配置
10. 路由和防火墙
13. 软件包管理
	1. [镜像挂卸载、rpm安装、配置yum本地源](chapter_06/day01.md)
	2. [程序编译与运行](chapter_06/day02.md)
	3. [宿主机和客户端文件输出](chapter_06/day03.md)
	4. [yum常用命令](chapter_06/day04.md)
	5. [rpm常用命令](chapter_06/day04.md)
	6. [maria数据库](chapter_06/day05.md)
16. shell编程
	1. [脚本调试](chapter_08/day08.md)
15. 服务器配置
	1. [nginx服务器之安装](chapter_09/day001.md)
	2. [nginx基本使用](chapter_09/day002.md)
	2. [apache服务器](chapter_09/day02.md)
	3. [DNS服务器](chapter_09/day03.md)
	4. [FTP服务器](chapter_09/day04.md)
	5. [docker]()
	6. [openstack]()
