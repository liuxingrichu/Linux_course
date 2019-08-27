## 系统用户接口 ##
#### 命令全称获取方式 ####
	- man 命令
	- info 命令
	- 互联网

#### 常用命令清单1 ####
1. 命令：ls（list）
	- 作用：查看当前目录下内容
- 命令：ll或ls -al
	- 作用：查看当前目录下内容的详细信息
	- 文件属性 

			-:文件
			l:连接文件
			d：目录
			r:read
			w：write
			x:execute
			-：无权限
			例如：rwx(Owner)r-x(Group)r-x(Other)
			十个格子，具体程序实现时，实际上是十个bit位。

	- 连接数
		- 一般文件：1
		- 做过硬链接的文件：硬链接次数 + 1
		- 目录：其内部全部目录个数（包括隐藏目录）+ 2（即当前目录和上层目录） 
	- 拥有者 
	- 所属的group 
	- 文件大小 
	- 建档日期 
	- 文件名　
- 命令：cat（catenate）
	- 作用：查看文件内容
- 命令：cd（Change Directory）
	- 作用：改变目录
	- 当前目录：.
	- 父目录：..
	- 绝对路径：从根目录开始，可用pwd（Print Working Directory）命令，查询
	- 相对路径
	- 常用例子
		1. 返回家目录	：cd
		2. 返回家目录	：cd ~
		3. 返回上一次目录	：cd -
		4. 到当前目录： cd .
		5. 到父目录： cd ..
		6. 到指定目录： cd 绝对路径
		7. 到指定目录： cd 相对路径
- 命令：wc（Word Count）
	- 作用：统计文件包含的行数、单词数和字符数
	- 常用flag：
		- 行数：-l（lines）
		- 单词数：-w（words）
		- 字符数：-m（chars）
- 命令：man（MANual pages ）
	- 作用：获取命令相关详细信息
- 命令：shutdown
	- 作用：关机或重启
	- 立即重启系统：shutdown -r  now (reboot)
	- 立即关闭系统：shutdown -h now (halt)
	- 10分钟后关闭系统: shutdown -h +10
- 命令：history
	- 作用：查询用户操作历史
	- 默认记录1000条记录，可以在文件/etc/profile中修改HISTSIZE的数值。
	- # history  10   （只列出最近10条记录）
	- # history | more（逐屏列出所有的历史记录）
	- # history  -c   （立即清空history当前所有历史命令的记录）
	- ![n]       执行历史命令
	- ！！     执行上一条命令
	- 用户级清除历史记录
		
			cd
			echo > .bash_history
			history -cw
	
	- 获取帮助信息
		- help history
	
	- 用户级自定制history信息显示格式
	
			cd 
			vim /root/.bashrc
				export HISTTIMEFORMAT="%F %T `whoami` "

- 命令：more
	- 作用：以一页一页的显示文件内容，方便使用者逐页阅读
	- 缺点：没有办法向前面翻， 只能往后面看
- 命令：less
	- 作用：主要用来浏览文件内容
	- 与more命令的用法相似，不同于more命令的是，less命令可往回卷动浏览以看过的部分

### 命令缩写参考清单 ###

	su：Swith user 切换用户，切换到root用户
	cat: Concatenate  串联
	uname: Unix name  系统名称
	df: Disk free  空余硬盘
	du: Disk usage 硬盘使用率
	chown: Change owner 改变所有者
	chgrp: Change group 改变用户组
	ps：Process Status  进程状态
	tar：Tape archive 解压文件
	chmod: Change mode 改变模式
	umount: Unmount 卸载
	ldd：List dynamic dependencies 列出动态相依
	insmod：Install module 安装模块
	rmmod：Remove module 删除模块
	lsmod：List module 列表模块
	alias :Create your own name for a command
	bash :GNU Bourne-Again Shell  linux内核 
	grep:global regular expression print
	httpd :Start Apache
	ipcalc :Calculate IP information for a host
	ping :Send ICMP ECHO_Request to network hosts
	reboot: Restart your computer
	sudo:Superuser do

	/bin = BINaries 
	/dev = DEVices 
	/etc = ETCetera 
	/lib = LIBrary 
	/proc = PROCesses 
	/sbin = Superuser BINaries 
	/tmp = TeMPorary 
	/usr = Unix Shared Resources 
	/var = VARiable ? 
	FIFO = First In, First Out 
	GRUB = GRand Unified Bootloader 
	IFS = Internal Field Seperators 
	LILO = LInux LOader 
	MySQL = My最初作者的名字SQL = Structured Query Language 
	PHP = Personal Home Page Tools = PHP Hypertext Preprocessor 
	PS = Prompt String 
	Perl = "Pratical Extraction and Report Language" = "Pathologically Eclectic Rubbish Lister" 
	Python Monty Python's Flying Circus 
	Tcl = Tool Command Language 
	Tk = ToolKit 
	VT = Video Terminal 
	YaST = Yet Another Setup Tool 
	apache = "a patchy" server 
	apt = Advanced Packaging Tool 
	ar = archiver 
	as = assembler 
	bash = Bourne Again SHell 
	bc = Basic (Better) Calculator 
	bg = BackGround 
	cal = CALendar 
	cat = CATenate 
	cd = Change Directory 
	chgrp = CHange GRouP 
	chmod = CHange MODe 
	chown = CHange OWNer 
	chsh = CHange SHell 
	cmp = compare 
	cobra = Common Object Request Broker Architecture 
	comm = common 
	cp = CoPy 
	cpio = CoPy In and Out 
	cpp = C Pre Processor 
	cups = Common Unix Printing System 
	cvs = Current Version System 
	daemon = Disk And Execution MONitor 
	dc = Desk Calculator 
	dd = Disk Dump 
	df = Disk Free 
	diff = DIFFerence 
	dmesg = diagnostic message 
	du = Disk Usage 
	ed = editor 
	egrep = Extended GREP 
	elf = Extensible Linking Format 
	elm = ELectronic Mail 
	emacs = Editor MACroS 
	eval = EVALuate 
	ex = EXtended 
	exec = EXECute 
	fd = file descriptors 
	fg = ForeGround 
	fgrep = Fixed GREP 
	fmt = format 
	fsck = File System ChecK 
	fstab = FileSystem TABle 
	fvwm = F*** Virtual Window Manager 
	gawk = GNU AWK 
	gpg = GNU Privacy Guard 
	groff = GNU troff 
	hal = Hardware Abstraction Layer 
	joe = Joe's Own Editor 
	ksh = Korn SHell 
	lame = Lame Ain't an MP3 Encoder 
	lex = LEXical analyser 
	lisp = LISt Processing = Lots of Irritating Superfluous Parentheses 
	ln = LiNk 
	lpr = Line PRint 
	ls = list 
	lsof = LiSt Open Files 
	m4 = Macro processor Version 4 
	man = MANual pages 
	mawk = Mike Brennan's AWK 
	mc = Midnight Commander 
	mkfs = MaKe FileSystem 
	mknod = MaKe NODe 
	motd = Message of The Day 
	mozilla = MOsaic GodZILLa 
	mtab = Mount TABle 
	mv = MoVe 
	nano = Nano's ANOther editor 
	nawk = New AWK 
	nl = Number of Lines 
	nm = names 
	nohup = No HangUP 
	nroff = New ROFF 
	od = Octal Dump 
	passwd = PASSWorD 
	pg = pager 
	pico = PIne's message COmposition editor 
	pine = "Program for Internet News & Email" = "Pine is not Elm" 
	ping =  Packet InterNet Grouper 
	pirntcap = PRINTer CAPability 
	popd = POP Directory 
	pr = pre 
	printf = PRINT Formatted 
	ps = Processes Status 
	pty = pseudo tty 
	pushd = PUSH Directory 
	pwd = Print Working Directory 
	rc = runcom = run command, shell 
	rev = REVerse 
	rm = ReMove 
	rn = Read News 
	roff = RunOFF 
	rpm = RPM Package Manager = RedHat Package Manager 
	rsh, rlogin, = Remote 
	rxvt = ouR XVT 
	sed = Stream EDitor 
	seq = SEQuence 
	shar = SHell ARchive 
	slrn = S-Lang rn 
	ssh = Secure SHell 
	ssl = Secure Sockets Layer 
	stty = Set TTY 
	su = Substitute User 
	svn = SubVersioN 
	tar = Tape ARchive 
	tcsh = TENEX C shell 
	telnet = TEminaL over Network 
	termcap = terminal capability 
	terminfo = terminal information 
	tr = traslate 
	troff = Typesetter new ROFF 
	tsort = Topological SORT 
	tty = TeleTypewriter 
	twm = Tom's Window Manager 
	tz = TimeZone 
	udev = Userspace DEV 
	ulimit = User's LIMIT 
	umask = User's MASK 
	uniq = UNIQue 
	vi = VIsual = Very Inconvenient 
	vim = Vi IMproved 
	wall = write all 
	wc = Word Count 
	wine = WINE Is Not an Emulator 
	xargs = eXtended ARGuments 
	xdm = X Display Manager 
	xlfd = X Logical Font Description 
	xmms = X Multimedia System 
	xrdb = X Resources DataBase 
	xwd = X Window Dump 
	yacc = yet another compiler compiler