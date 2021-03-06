### 监视进程之top ###
top命令默认在一个特定间隔(3秒)后刷新显示。要手动刷新，用户可以输入回车或者空格。


	选项
		-c 			显示完整的命令
		-d <时间> 	设置间隔时间
		-u <用户名> 	指定用户名
		-p <进程号> 	指定进程
		-n <次数> 	循环显示的次数

	设置信息更新时间
		语法 top -d <时间>
		$ top -d 5 		//表示更新周期为5秒
	设置循环显示的次数
		语法 top -n <次数> 
		$ top -n 2
		$ top -d 5 -n 2 > top.txt			

- top命令
	1. 语法：top  [选项]
	2. 功能：top命令提供了对系统处理器实时的状态监视，显示系统中活跃的进程列表，可以按CPU、内存以及进程的执行时间对进程进行排序，通常会全屏显示，而且会随着进程状态的变化而不断更新。


- top显示界面信息
	- 第一行是服务器基本信息，包括top命令的刷新时间为9:34:51，系统已经启动的时间为1天46分钟，当前有3个用户，系统负载为：最近1分钟内的平均系统负载为0.00，最近5分钟内的平均系统负载为0.01，最近15分钟内的平均系统负载为0.05（这说明系统基本是闲置的）。越小代表系统越闲置。若高于1，要注意系统压力是否太过负担太重。
	- 第二行是当前系统进程概况，一共有103个进程，其中一个正在运行中，102个出于休眠，没有停止的进程，没有僵尸进程。
	- 第三行是CPU信息，us代表用户空间占用的CPU百分比，sy代表内核空间占用的CPU百分比，ni代表改变过优先级的进程占用的CPU百分比，id代表空闲CPU百分比，wa代表I/O等待百分比，hi代表硬中断占用的CPU百分比，si代表软中断占用的CPU百分比。st Steal time 虚拟机被hypervisor偷去的CPU时间（如果当前处于一个hypervisor下的vm，实际上hypervisor也是要消耗一部分CPU处理时间的）。现在计算机一般有多核CPU，要想查看每个逻辑CPU的使用情况，可以在top显示界面中按数字键1。
	- 第四行是物理内存的使用状态，从左到右分别表示物理内存总量，空闲内存，已使用的内存，缓存使用的内存。
	- 第五行是虚拟内存的使用状态，从左到右分别表示物理内存总量，空闲内存，已使用的内存，缓存的交换区总量。注意swap使用量要尽量少！若swap被大量使用，表示系统的物理内存实在不足！

	- 再往下的所有信息就是动态的进程信息了。
	- 进程信息区中信息只是top默认显示的12个字段。
	- 若想显示更多的字段，可以在top显示界面中按字母键f。按该键后，前面带*号的就是当前显示的字段。要想显示更多的字段，可以选择该行后，通过按键“空格”或“d”，进行取消显示或设置显示。设置完成后按“Esc”或“q”键，退出设置界面，进入top显示界面。
	- 默认情况下，top显示的进程是按照CPU使用率来进行排序的。若另选排序规则，需要在top显示界面中按字母键f。按该键后，“s”键设置top显示界面的排序。


- 退出top显示界面方法
	- 按键“q”
	- 组合键“Ctrl”+"c"

- top显示页面快捷键
	- 按字母P键：表示按照CPU的使用率排序
	- 按字母M键：表示按照Memory的使用率排序
	- 按字母N键：表示以PID排序
	- 按字母T键：表示按照CPU使用时间排序
	- 注意快捷键是区分大小写的

- top交互命令
	- 进入方式：在top显示页面，按“h”或“？”键。
	- 按键“k”：杀进程
	- 按键“W”：保持用户设置到~/.toprc文件中，下次用户进入top显示界面时，就按照之前的配置。




