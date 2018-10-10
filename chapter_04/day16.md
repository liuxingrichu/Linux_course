### 例行任务管理之at、batch ###
0. 确定atd是否正常运行
	1. yum install at -y
	2. service atd status
	3. service atd start
	4. service atd status
	5. 设置开机自启动atd服务
		1. chkconfig atd on
1. 单一时刻执行一次任务：at
	1. 语法：at  [选项]  时间
	2. 功能：at命令可以让用户在指定时间执行某个程序或命令。
	3. TIME的格式是HH:MM [MM/DD/YY]，其中HH是小时，MM是分钟，如果要指定超过一天内的时间，那么可以用MM/DD/YY，其中MM 是月，DD是日，YY是年。
	4. 使用方法：执行第1条命令（指定时间），进入at命令的交互模式，输入在指定时间要执行的命令，然后按下【Ctrl+D】键退出at命令的交互模式。可以输入多个命令。建议使用绝对路径来执行命令，可降低出错概率。
	5. 注意点：不超过当天只写时间就可 ，否则需要依次输入月日年。
2. 查询当前用户任务列表
	1. atq
3. 删除已经进入任务队列的任务
	1. atrm <任务号>
4. 查询at进程信息
	1. ps -ef | grep <username> | grep at | grep -v grep 

			举例：
				设置30分钟后自动关机
					$ at now + 30 minutes
						at> shutdown -h now
						at> <EOT>
						job 6 at Wed Oct 10 17:01:00 2018
					$ atq
						6       Wed Oct 10 17:01:00 2018 a fsp
					$ atrm 6


 				at 00:00 2018-10-11
				at 4:00 10/12/2018

5. 说明
	1. 默认情况下，所有用户都可以使用at命令来调度自己的任务。
	2. 若由于特殊原因，需要禁止某些用户使用这个功能，可以将该用户的用户名添加至/etc/at.deny中。

6. at运行方式
	1. 使用at命令来生成所要运行的工作，并将这个工作以文本文件的方式写入/var/spool/at/目录内，该工作便能等待atd服务的取用与执行。
	2. 可使用/etc/at.allow与/etc/at.deny这两个文件，来进行at的使用限制。加上这两个文件后，at的工作流程是：
		1. 先寻找/etc/at.allow这个文件，写在这个文件中的用户，才能使用at。没有在这个文件中的用户，则不能使用at（即使没有写在at.deny当中）。
		2. 若/etc/at.allow不存在，就寻找/etc/at.deny文件。若写在这个文件中的用户，则不能使用at，而没有在at.deny文件中的用户就可以使用at。
		3. 若两个文件都不存在，那么只有root可以使用at命令。

7. 查询第3项工作内容
	1. at -c 3

at的执行与终端机环境无关，而所有标准输出、标准错误的输出都会传递到执行者的mailbox。若你在tty1登录，想echo输出信息，可以使用echo "hello" > /dev/tty1。

at创建的任务，会在后台执行。

由于在at工作调度的使用上，系统会将该项at工作独立出你的bash环境中，直接交给系统的atd程序来接管。因此，当执行了at的工作后，就可以立刻脱机了，剩下的工作就完成交给Linux管理。所以，若有长时间的网络工作时，使用at可以让你免除网络断线后的困扰。

### batch ###
- 系统空闲时，才进行后台任务：batch
	- 它会在CPU工作负载小于0.8时，才进行需要执行的工作任务。
	- 负载：CPU在单一时间点所负载的工作数量，不是CPU的使用率。
	- 当CPU的工作负载越大，代表CPU必须要在不同的工作之间进行频繁的工作切换。
	- batch的使用方式与at一样，也通过atq查询任务，atrm删除任务。

			# batch
				at> echo "hi" > /dev/tty1
				at> <EOT>
				job 22 at Wed Oct 10 19:26:00 2018
			# atq
			# atrm 6
