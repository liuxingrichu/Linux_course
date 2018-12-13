### 网络监测 ###
1. 实现实验室网络监测，并输出监测信息

		vim check_network.sh
	
			#!/bin/bash
			
			IP='192.168.1'
			
			for i in `seq 2 254`
			do
			        ping -c1 -w1 $IP.$i &>/dev/null && echo "$IP.$i is up" || echo "$IP.$i is down"
			done

2. 需求：检测实验室环境下，动态IP使用情况，同时分类存放，并汇总输出。

		#!/bin/bash
		# test IP status
		
		IP='192.168.1'
		used_num=0
		unused_num=0
		
		for i in `seq 2 254`
		do
		    ping -c 3 $IP.$i &>/dev/null 
			if [ $? -eq 0 ]; then
				let "used_num+=1"
				echo "$IP.$i" >> used_IP_list.log
			else
				let "unused_num+=1"
				echo "$IP.$i" >> unused_IP_list.log
			fi
		done
		echo "used IP number: $used_num"
		echo "unused IP number: $unused_num"



		测试结果：
			time sh -x network_check.sh

				+ IP=192.168.1
				+ used_num=0
				+ unused_num=0
				++ seq 2 254
				+ for i in '`seq 2 254`'
				+ ping -c 3 192.168.1.2
				+ '[' 1 -eq 0 ']'
				+ let unused_num+=1
				+ echo 192.168.1.2
				+ for i in '`seq 2 254`'
				+ ping -c 3 192.168.1.3
				......
				+ ping -c 3 192.168.1.253
				+ '[' 1 -eq 0 ']'
				+ let unused_num+=1
				+ echo 192.168.1.253
				+ for i in '`seq 2 254`'
				+ ping -c 3 192.168.1.254
				+ '[' 1 -eq 0 ']'
				+ let unused_num+=1
				+ echo 192.168.1.254
				+ echo 'used IP number: 4'
				used IP number: 4
				+ echo 'unused IP number: 249'
				unused IP number: 249
				
				real    12m47.826s
				user    0m0.758s
				sys     0m1.269s

