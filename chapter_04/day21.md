### 系统或硬件时间: date hwclock clock ###
Linux时钟分为系统时钟和硬件时钟。系统时钟是指当前Linux Kernel中的时钟，而硬件时钟则是主板上由电池供电的时钟，这个硬件时钟可以在BIOS中进行设置。当Linux启动时，系统时钟会去读取硬件时钟的设置，然后系统时钟就会独立于硬件运作。

- 进入BIOS系统的方法
	- 华硕：F2
	- 惠普：F10

Linux中的所有命令，都是采用系统时钟。

如果需要以指定的格式显示日期，可以使用“+”开头的字符串指定其格式。


- 输出格式控制符
	- %Y表示年
	- %m表示月
	- %d表示日
	- %H表示小时
	- %M表示分钟
	- %S表示秒，表示从 1970 年 1 月 1 日 00:00:00 UTC 到目前为止的秒数，
	- %w表示一周中的第几天。

- hwclock: 查看硬件时间
	- 获取帮助信息：
		- hwclock -h
		- man hwclock
	- 将硬件时间写入到系统时间：hwclock -s
	- 将系统时间写入到硬件时间：hwclock -w
- clock: 查看硬件时间，功能类型hwclock。
- date：查看系统时间
	- 选项-s： 可以设置系统时间
		- # date -s "2008-08-08 20:00:00"
		- # date -s "19911005 8:00:00"
		- # date -s "2028/08/08 20:00:00"
	- 时间同步方法
		- 安装rdate
			- # yum install rdate -y
			- # rdate -s time-b.nist.gov
		- 使用date命令设置
	- 指定显示日期格式：使用“+”开头的字符串指定其格式
		- $ date "+%Y-%m-%d %H:%M:%S"
		- $ date "+%Y-%m-%d %H:%M:%S" -d "-3 year"
		- $ date "+%Y-%m-%d %H:%M:%S" -d "+3 month"
		- $ date "+%Y-%m-%d %H:%M:%S" -d "+10 day"


