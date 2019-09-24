### 进程管理（上）之练习题 ###
1. 查看系统中所有进程，并统计进程数。
2. 查看当前系统进程的uid、pid、stat、pri,以uid排序 。
3. 动态显示进程信息。
4. 将父进程信息添加到动态进程信息显示中。
5. 对动态进程信息按照内存使用率排序。
6. 将 top 的信息运行3次，然后将结果输出到家目录下top.txt文件中。


		1. 查看系统中所有进程，并统计进程数。
		
			ps -A | wc -l
			ps -e | wc -l
			ps -ef | wc -l
			ps -elf | wc -l
			ps -aux | wc -l
			ps aux | wc -l
		
			ps -e > ps.txt
			vim ps.txt
			查看文件行号

			top命令输出信息中，查看总进程数。

			说明：
				1. 文件查看行数方式，比top里面的进程数多一个，其原因为第一行为列显示信息。
				2. wc统计行数，比top里面的进程数多两个，其原因为第一行为列显示信息，另外一个为wc命令启动了一个进程。
		
		2. 查看系统所有进程的user、uid、gid、pid、ppid、ni、cmd,以uid排序。

			ps -eo user,uid,gid,pid,ppid,ni,cmd --sort uid
		3. 动态显示进程信息。
		
			top
		
		4. 将父进程信息添加到动态进程信息显示中。
		
			执行top命令，按“f”键，选中父进程，按“空格”或“d”键，再按“Esc”键即可。
		5. 对动态进程信息按照内存使用率排序。
		
			方法一：执行top命令，按“f”键，选中内存使用率，按“s”键，再按“Esc”键即可。
			方法二：执行top命令，按“M”键
		
		6. 将 top 的信息运行3次，然后将结果输出到家目录下top.txt文件中。
		
			cd
			top -n 3 > top.txt
			或
			top -n 3 > ~/top.txt



