### 脚本调试 ###
1. 编写脚本

		#!/bin/bash
		
		IP='10.103.79'
		
		for i in `seq 1 10`
		do
		        ping -c1 -w1 $IP.$i &>/dev/null && echo "$IP.$i is up" || echo "$IP.$i is down"
		done
2. 运行脚本

		# sh -x check_network.sh