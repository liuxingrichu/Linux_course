### C编译和运行 ###
1. 编写程序


		#include<stdio.h>
		
		int main()
		{
		        printf("hello world!\n");
		        return 0;
		}

2. 编译程序

		# gcc -o hello hello.c
3. 运行程序

		# ./hello
		# /home/admin/hello

### Java编译和运行 ###
1. 需求分析
	1. 安装环境的系统
	2. 安装环境的位数
		1. Linux系统

				# getconf LONG_BIT
				# uname -a
2. 下载java环境安装包
	1. 登陆https://www.oracle.com/technetwork/java/javase/downloads/jdk10-downloads-4416644.html
	2. 下载jdk-10.0.2_linux-x64_bin.tar.gz
3. 传输到Linux系统
4. 登陆Linux系统，执行一下命令

		# mkdir /usr/java	
		# cd /home/admin
		# tar -zxvf jdk-10.0.2_linux-x64_bin.tar.gz -C /usr/java/
5. 配置java环境变量
	1. 全局生效
		1. 打开/etc/profile文件，再最后输入以下内容

				export JAVA_HOME=/usr/java/jdk-10.0.2
				export CLASSPATH=.:${JAVA_HOME}/lib
				export PATH=$PATH:${JAVA_HOME}/bin
		2. 配置文件生效

				# source /etc/profile
	2. 局部生效
		1. 在～/.profile中添加，“～/”表示当前用户的主目录，所以在这个文件中添加只能对当前用户可见，其他用户不可见

    	2. 在～/bashrc中添加，同1，不再赘述

6. 测试
	1. 安装环境测试

			# java -version
	2. 运行环境测试
		1. 编写java程序
	
				# vim Test.java
			
					public class Test{
					        public static void main(String args[]){
					                System.out.println("hello world!");
					        }   
					}
		2. 编译
	
				# javac Test.java
		3. 运行
	
				# java Test

