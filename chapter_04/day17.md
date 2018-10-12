### 例行任务管理之cron ###
周期性执行任务

1. 确定crond进程是否运行正常
	1. service crond status
2. 编辑crontab的工作内容：crontab -e
3. 删除所有crontab工作内容：crontab -r
4. 查看所有crontab工作内容：crontab -l
5. 仅root用户可以使用-u参数，查看指定用户的任务。其他用户仅能设置、查看、删除自己的计划任务。

		例如：
			# crontab -u fsp -l
			
		语法：设置crontab的基本格式如下：
			* * * * * command

			编辑执行的时间和执行的命令。
			前面5个*可以用来定义时间。
			第一个*表示分钟，可以使用的值是0-59，每分钟可以使用*或*/1表示。
			第二个*表示小时，可以使用的值是0-23。
			第三个*表示日期，可以使用的值是1-31。
			第四个*表示月份，可以使用的值是1-12。
			第五个*表示星期几，可以使用的值是0-6或1-7，0或7代表星期日。
			最后是执行的命令。

		举例：
			* * * * * ps -l
			* * * * * echo "hello, cron" > /dev/tty1
			* * * * * date > /dev/tty1

		每分钟重启crond进程
			* * * * * service crond restart
			*/1 * * * * service crond restart
		每小时重启crond进程
			0 */1 * * * service crond restart
		从23点开始到3点，每小时重启crond进程？
			0 23-3/1 * * * service crond restart
		每天晚上23:30重启crond进程
			30 23 * * * service crond restart
		每月的第一天晚上23:30重启crond进程
			30 23 1 * * service crond restart
		每年的1月1日的晚上23:30重启crond进程
			30 23 1 1 * service crond restart
		每周日晚上23:30分重启crond进程
			30 23 * * 0 service crond restart


当到了设定的时间，系统会自动执行定义好的命令。执行命令最好使用绝对路径。

- 安全性问题
	- 默认，每个用户都可以设置自己的crontab。
	- 若由于特殊原因需要禁止某些用户使用这个功能，可以将该用户添加至/etc/cron.deny中。
	- /etc/cron.allow
		- 将可以使用crontab账号的写入其中，若不在这个文件中的用户，则不可使用crontab。
	- /etc/cron.deny
		- 将不可以使用crontab的账号写入其中，若未记录到这个文件中的用户，就可以使用crontab。
	- 与at很像，以优先级来说，/etc/cron.allow比/etc/cron.deny要优先，而判断方面，上面两个文件仅选择一个来限制即可。建议仅保留一个，避免影响自己在设置上面的判断。
	- 一般来说，系统默认是保留/etc/cron.deny，可以将不想执行crontab的那个用户写入/etc/cron.deny当中，一个账号一行！！！
	- 使用crontab命令创建的工作调度，工作内容会被记录到/var/spool/cron/里面，而且用账号作为判别的。但不要使用vim直接编辑该文件，因为可能由于输入语法错误，会导致无法执行cron。每个用户都只有一个文件存在。
	- cron执行的每一项工作，都会被记录到/var/log/cron这个目录中。若判定Linux系统是否被植入木马，可参阅查询/var/log/cron这个日志文件。

- 监测机制
	- cron服务最低检测是“分钟”，所以cron会每分钟去读取一次/etc/crontab与/var/spool/cron里面的数据内容。因此，编辑完周期性任务后，将其保存后，cron设置就自动生效了，但有些发布版本，其crontab是读取到内存中的，保险起见可以重新启动crond服务。
### 不同来源的例行任务 ###
通过crontab -e 命令，可以创建用户自己的例行周期任务。其生成可执行文件/usr/bin/crontab。

通过配置/etc/crontab文件，该文件为纯文本文件，root身份可以编辑该系统的例行任务。

	# cat /etc/crontab
		SHELL=/bin/bash
		PATH=/sbin:/bin:/usr/sbin:/usr/bin
		MAILTO=root
		
		# For details see man 4 crontabs
		
		# Example of job definition:
		# .---------------- minute (0 - 59)
		# |  .------------- hour (0 - 23)
		# |  |  .---------- day of month (1 - 31)
		# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
		# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
		# |  |  |  |  |
		# *  *  *  *  * user-name  command to be executed

	前5个*号作用与crontab -e的用户自定制例行周期任务一致
	user-name表示以什么身份执行例行任务
	若有第7列，为run-parts，表示使用run-parts方式来运行例行任务，该方式指定目录下的所有文件都执行！；若没有第7列，表示使用命令模式运行例行任务。
	command to be executed表示运行的例行任务，或目录（run-parts）

- 配置方式
	1. 直接执行命令

			举例：
				* * * * * fsp echo "hello, fsp"
	2. 以目录来规划

			举例：
					*/5 * * * * root run-parts /etc/cron.min
				首先，创建目录/etc/cron.min，将每隔5分钟执行的“可执行文件”都写到该目录下。
				其次，在/etc/crontab文件中书写上面周期性任务。
				这样，系统就每5分钟执行一次该目录下的所有可执行文件。

- 注意：
	- 周与日、月不可同时并存

			例如：
	
				30 12 11 9 5 root echo “hello”
			
				系统执行效果，可能存在与预期不一致。