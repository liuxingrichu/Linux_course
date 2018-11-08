### nginx服务器 ###
1. 需求分析
2. 源码包下载
	1. 登陆http://nginx.org/en/download.html
	2. 下载nginx-1.12.2.tar.gz
3. Linux系统安装

		# tar -zxvf nginx-1.12.2.tar.gz
		# cd nginx-1.12.2
		# ./configure --prefix=/usr/local/nginx
		# yum -y install gcc gcc-c++ autoconf automake make
		# yum install pcre
		# yum install pcre-devel
		# yum install -y zlib
		# yum install -y zlib-devel
		# ./configure --prefix=/usr/local/nginx
		# make && make install
		# cd /usr/local/nginx/

		conf -----配置文件
		html -----网页文件
		logs -----日志文件
		sbin -----主要二进制程序

4. 服务启动
	1. 启动服务：service nginx start
	2. 停止服务：service nginx stop
	3. 重读配置：service nginx reload
	4. 重启服务：service nginx restart
	5. 服务状态：service nginx status
	6. 文件测试：service nginx configtest
5. 查询
	1. # netstat -antp

6. 测试
	1. 关闭防火墙：# systemctl stop firewalld.service
	2. 客户端访问：http://10.103.79.7/
	3. 配置个人主页
		1. 将自己的index.html文件替换到/usr/local/nginx/html目录下的index.html。

#### 场景1 ####
问题现象：在centos 7下启动nginx出现Failed to start nginx.service:unit not found

问题定位：没有添加nginx服务，所以启动失败。

解决方案：
1. 创建文件/etc/init.d/nginx，并输入以下内容

		#!/bin/sh
		# nginx - this script starts and stops the nginx daemin
		#
		# chkconfig:   - 85 15
		
		# description:  Nginx is an HTTP(S) server, HTTP(S) reverse \
		#               proxy and IMAP/POP3 proxy server
		
		# processname: nginx
		# config:      /usr/local/nginx/conf/nginx.conf
		# pidfile:     /usr/local/nginx/logs/nginx.pid
		
		# Source function library.
		
		. /etc/rc.d/init.d/functions
		
		# Source networking configuration.
		
		. /etc/sysconfig/network
		
		# Check that networking is up.
		
		[ "$NETWORKING" = "no" ] && exit 0
		
		nginx="/usr/local/nginx/sbin/nginx"
		
		prog=$(basename $nginx)
		
		NGINX_CONF_FILE="/usr/local/nginx/conf/nginx.conf"
		
		lockfile=/var/lock/subsys/nginx
		
		start() {
		
		    [ -x $nginx ] || exit 5
		
		    [ -f $NGINX_CONF_FILE ] || exit 6
		
		    echo -n $"Starting $prog: "
		
		    daemon $nginx -c $NGINX_CONF_FILE
		
		    retval=$?
		
		    echo
		
		    [ $retval -eq 0 ] && touch $lockfile
		
		    return $retval
		
		}
		
		
		stop() {
		
		    echo -n $"Stopping $prog: "
		
		    killproc $prog -QUIT
		
		    retval=$?
		
		    echo
		
		    [ $retval -eq 0 ] && rm -f $lockfile
		
		    return $retval
		
		}
		
		
		
		restart() {
		
		    configtest || return $?
		
		    stop
		
		    start
		
		}
		
		
		reload() {
		
		    configtest || return $?
		
		    echo -n $"Reloading $prog: "
		
		    killproc $nginx -HUP
		
		    RETVAL=$?
		
		    echo
		
		}
		
		force_reload() {
		
		    restart
		
		}
		
		
		configtest() {
		
		  $nginx -t -c $NGINX_CONF_FILE
		
		}
		
		
		
		rh_status() {
		
		    status $prog
		
		}
		
		
		rh_status_q() {
		
		    rh_status >/dev/null 2>&1
		
		}
		
		case "$1" in
		
		    start)
		
		        rh_status_q && exit 0
		        $1
		        ;;
		
		    stop)
		
		
		        rh_status_q || exit 0
		        $1
		        ;;
		
		    restart|configtest)
		        $1
		        ;;
		
		    reload)
		        rh_status_q || exit 7
		        $1
		        ;;
		
		
		    force-reload)
		        force_reload
		        ;;
		    status)
		        rh_status
		        ;;
		
		
		    condrestart|try-restart)
		
		        rh_status_q || exit 0
		            ;;
		
		    *)
		
		        echo $"Usage: $0 {start|stop|status|restart|condrestart|try-restart|reload|force-reload|configtest}"
		        exit 2
		
		esac

2. 对/etc/init.d/nginx文件进行配置

		# cd /etc/init.d
		# chmod 755 /etc/init.d/nginx
		# chkconfig --add nginx   (注意add前面是两个短横线-)

#### 场景2 ####
1. 执行启动nginx服务：# service nginx start
2. 现象：
Starting nginx (via systemctl):  Job for nginx.service failed because the control process exited with error code. See "systemctl status nginx.service" and "journalctl -xe" for details.
                                                           [FAILED]
3. 问题定位：apache服务占有了80端口。

		# service httpd status

			Redirecting to /bin/systemctl status httpd.service
			● httpd.service - The Apache HTTP Server
			   Loaded: loaded (/usr/lib/systemd/system/httpd.service; disabled; vendor preset: disabled)
			   Active: active (running) since Mon 2018-09-03 02:03:25 CST; 1h 15min ago
4. 解决方案：
	1. 关闭apache服务：# service httpd stop
	2. 查询端口信息：# netstat -antp
	3. 启动nginx服务：# service nginx start
