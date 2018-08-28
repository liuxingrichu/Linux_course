### Java开发环境配置 ###
1. 下载源码包
	1. https://www.oracle.com/technetwork/java/javase/downloads/jdk10-downloads-4416644.html
		1. 最好选择tar.gz压缩包，这个是源码包，安装的时候进行编译链接，适用于各种Linux版本。
		2. rpm相当于windows下的安装包，事先编译好了的，有环境限制。
2. 上传至Linux系统
3. 源码安装或rpm包安装
	1. Ctrl+alt+t，打开terminal
    2. cd /usr，到/usr目录下（因为Linux中一般的用户软件都安装在这个目录下）
    3. sudo mkdir Java，创建一个名为Java的目录
    4. 把之前下载的jdk移动到 /usr/Java 目录下
    5. 在这个Java目录中，sudo tar -zxvf  jdk-8u121-linux-x64.tar.gz（关于tar命令可以自行输入“man tar”查看其用法），解压后生成当前jdk版本的一个目录
4. 配置java环境
	1. 在～/.profile中添加，“～/”表示当前用户的主目录，所以在这个文件中添加只能对当前用户可见，其他用户不可见

    2. 在～/bashrc中添加，同1，不再赘述

    3. 在/etc/profile中添加，在这个文件中添加对所有用户可见

        添加代码如下：

                JAVA_HOME=/usr/Java/jdk1.8.0_121

                JRE_HOME=$JAVA_HOME/jre
                CLASSPATH=.:$JRE_HOME/lib:$JAVA_HOME/lib
                PATH=$PATH:$JAVA_HOME/bin
                export PATH JAVA_HOME CLASSPATH

        修改保存后需要输入命令：source /etc/profile更新一下配置
5. 测试
	1. 安装环境测试
		1. java -version
	2. 运行环境测试
		1. 编写一个简单的Test.java程序，先javac Test.java编译一下，然后java Test运行

