### 进程管理（中）之练习 ###
1. 分别用pgrep, pidof, ps | grep命令搜索bash进程。
2. 分别使用kill，killall,pkill命令删除bash进程。
3. 调整bash进程的nice值至-10。
4. 以nice值为7，运行命令“ps -l”
5. 查询当前命令运行的nice值。
6. 创建并打开文件tmp.log，输入“hello”，将其进程放入后台。查询其进程PID号，查询后台进程信息，并将其进程切换至前台，不保存关闭文件。



		1. 分别用pgrep, pidof, ps -ef | grep命令搜索bash进程。
		
				pgrep bash
				pidof bash
				ps -ef | grep bash
		2. 分别使用kill，killall,pkill命令删除bash进程。
		
				ps -ef | grep bash
				kill <PID>
				kill -9 <PID> 
				# killall bash
				# killall -9 bash 
				# pkill bash
				# pkill -9 bash
		3. 调整bash进程的nice值至-10。

			ps -ef | grep bash
			# ps -l
			# renice -10 <PID>
			# ps -l
			

		4. 以nice值为7，运行命令“ps -l”

			nice -n 7 ps -l
 
		5. 查询当前命令运行的nice值。

			nice
		6. 创建并打开文件tmp.log，输入“hello”，将其进程放入后台。查询其进程PID号，查询后台进程信息，并将其进程切换至前台，不保存关闭文件。

			vim tmp.log
				hello
			Ctrl+z
			ps -lf | grep tmp
			pidof vim
			pgrep vim
			jobs
			fg
			:q!

