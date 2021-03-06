## 系统用户接口 ##
### 通配符 ###
常用通配符有.，*，？，[], [^]。

	# vim auto_touch.sh
		#!/bin/bash
		for i in `seq 1 10`
		do
		        touch ztg$i.txt
		done


1. 默认匹配除\n之外的任意一个字符:点(.)
2. 贪婪匹配前一个字符的0次或多次：*
	1. 例如:# ls *.txt
2. 贪婪匹配前一个字符1次或0次：?
	1. 例如：# # ls ztg?.txt
3. 区间范围内的任意一个字符：[]
	1. 例如：# ls ztg[1-9].txt
	2. 例如：# ls ztg[123].txt
4. 匹配不是中括号里面的一个字符
	1. 例如：# ls ztg[^123].txt

### 重定向 ###
1. 标准输入设备（默认输入设备）：键盘
2. 标准输出设备（默认输出设备）：显示器
3. 重定向
	1. 将原本应该从标准输入设备输入的数据，改为其他文件或设备输入。
	2. 将原本应该输出到标准输出设备的内容，改为输出到其他文件或设备上。
4. 文件标识符
	1. 标准输入：0
	2. 标准输出：1
	3. 标准错误输出：2
5. I/O重定向符号
	1. 标准输出覆盖重定向（先清空，再输入）：>
		
			例如：
				$ ll > info.txt
	2. 标准输出追加重定向：>>

			例如：
				$ ll >> info.txt 
				$ llh >>in.txt 2>>err.txt
	3. 标识输出重定向：>&

			例如：
				$ start > info.txt 2>&1
				$ llh &>> djdj.txt
				# tailf /var/log/messages >> msg.log 2>&1 &
	4. 标准输入重定向：<
			
			例如：
				$ cat < info.txt
			多用于脚本数据输入，从默认的键盘输入，修改为文件。
	
	5. 标准输入重定向： <<
		
			通过cat>file来创建文件，并将内容输入文件，输入结束后，按下快捷键“Ctrl+d”结束输入。
			[fsp@localhost ~]$ cat > file
			hello everyone
			this is a book
			[fsp@localhost ~]$ cat file
			hello everyone
			this is a book
			[fsp@localhost ~]$
			使用<<让系统将一次键盘的全部输入，先送入虚拟机的“当前文档”，然后一次性输入。可以选择任意符号作为终结标识符。
			[fsp@localhost ~]$ cat > file << quit
			> hello
			> quit
			[fsp@localhost ~]$ cat file
			hello
			[fsp@localhost ~]$


### 管道 ###
1. 管道也是一种重要的I/O重定向方法。
2. 管道就是将一个命令的输出作为另一个命令的输入。
3. 管道符号：|

### KDE（K Desktop Environment）与GNOME（The GNU Network Object Model Environment） ###
KDE和GNOME都是基于X Window的图形窗口管理系统。

X Window系统并不是一个软件，而是一个协议，这个协议定义一个系统所必须具备的功能。任何系统只要满足此协议的规范要求，就成为X。

X Window是Linux下的图形用户界面，它可以简化系统和网络管理工作，使操作更加直观和简便。

KDE桌面和GNOME桌面，它的主要部分是一个拥有任务条、工具条和快捷图标的桌面环境，并且包括可用于浏览网页的文件管理器、编辑器、计算器和邮件处理程序等大量的应用程序。
