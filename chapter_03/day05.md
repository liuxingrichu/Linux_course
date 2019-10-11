### 配置vim编辑器（vim = vi improved） ###
1. 全局生效

		# vim /etc/vimrc
		
		在文件最后添加，以下语句
			set nu         // 设置显示行号
		   	set showmode   //设置在命令行界面最下面显示当前模式等。
		   	set ruler     // 在右下角显示光标所在的行数等信息
		   	set autoindent   // 设置每次单击Enter键后，光标移动到下一行时与上一行的起始字符对齐
		   	syntax on    // 即设置语法检测，当编辑C或者Shell脚本时，关键字会用特殊颜色显示

2. 当前用户生效
	- 在用户登录的 ~ 目录下创建一个 .vimrc文件，在其中进行自己习惯的编程环境的设置，这样当别的用户使用实并不互相影响。


### source /etc/vimrc报错 ###

编辑完vimrc之后，使用source /etc/vimrc之后报错：

	$ source /etc/vimrc
	bash: /etc/vimrc: line 15: syntax error near unexpected token `"autocmd"'
	bash: /etc/vimrc: line 15: `if has("autocmd")'

主要是因为：
vimrc是vim启动时解释的，而不是由shell来解释。用shell来source它肯定不行

解决办法：其实根本不用source等任何操作，使用vi时候自动读取配置，如果还是没有生效，那么就拷贝一个vimrc到你的目录（HOME或者WORK目录即可）下，命名为 .vimrc即可 



### vim编辑器 ###
1. 显示行号
	1. set nu
	2. set number
2. 关闭显示行号
	1. set nonu
	2. set nonumber
3. 查看vim教程
	- vimtutor

- 文件创建或打开
	- vim files
- 光标移动操作	
	- G	移动到整个文件的末尾
	- :n（n是一个数字）	移动到第n行	
- 输入模式（编辑操作）	
	- dd	删除光标所在行
	- ndd（n是一个数字）	删除包含光标所在行在内的n行文字
	- yy	复制关标所在的行
	- nyy（n是一个数字）	复制连同光标所在行在内的n行文字
	- p	将复制的文本粘贴在光标下面一行
	- u	撤销操作
	- i	在当前光标处添加内容
	- o	在当前光标下一行插入新行并开始编辑
	- a	在当前光标后一个字符开始添加内容
- 末行模式
	- :q
	- :q!
	- :wq
	- :wq!
- 可视化模式
	- v
- 查询模式
	- /
	- ?
	- n/N

查询关键字还可以使用“？”符合，和“/”不同之处是，“？”查询默认是从光标位置向上寻找关键字，按n键代表继续往上寻找，按N键代表向下寻找。


- vim拥有5种编辑模式
	- 命令模式：初始状态，其他模式下按下esc键
	- 输入模式：命令模式下按下a、i、o或A  、I 、O键
	- 末行模式：命令模式下输入“：”
	- 可视化模式：命令模式下按下V键
	- 查询模式：命令模式下输入 “/”“？” 字符

### Vim: 警告: 输出不是到终端(屏幕) ###

- 执行操作：
	
		$ `vim abc`

- 输出信息：
	- Vim: 警告: 输出不是到终端(屏幕)	
	- Vim: Warning: Output is not to a terminal
- 现象：
	- Ctrl+c和q都不可终止其运行状态。
- 原因：
	- 其运行的进程不在前台，启动了子进程，Ctrl+c等操作的命令，无法发送给子进程。
- 解决方法：
	1. 若现象发生在远程连接，关闭远程连接，再重新远程连接即可。
	2. 若在虚拟终端上发生，可在其他虚拟终端或远程连接中，通过进程搜索，关闭其进程，会发现shell前台运行异常。可以将其bash进程也强制关闭，重新登录即可。


　