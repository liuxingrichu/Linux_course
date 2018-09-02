### 配置vim编辑器 ###
1. 全局生效

		# vim /etc/vimrc
		
		在文件最后添加，以下语句
			set nu         // 这是设置显示行号
		   	set  showmode   //设置在命令行界面最下面显示当前模式等。
		   	set   ruler     // 在右下角显示光标所在的行数等信息
		   	set autoindent   // 设置每次单击Enter键后，光标移动到下一行时与上一行的起始字符对齐
		   	syntax on    // 即设置语法检测，当编辑C或者Shell脚本时，关键字会用特殊颜色显示

2. 当前用户生效
	- 在用户登录的 ~ 目录下创建一个 .vimrc文件，在其中进行自己习惯的编程环境的设置，这样当别的用户使用实并不互相影响。

### vim常用命令 ###
1. 显示行号
	1. set nu
	2. set number
2. 关闭显示行号
	1. set nonu
	2. set nonumber