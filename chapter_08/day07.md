### 判断 ###
1. if判断结构

		if expression; then
			command
		fi
		
		若expression测试返回真，则执行command。
		若要执行的不止一条命令，则不同命令间用换行符隔开。

2. if/else判断结构

		if expression; then
			command
		else
			command
		fi

3. if/elif/else判断结构

		if expression1; then
			command1
		else
			if expression2; then
				command2
			else
				command3
			fi
		fi
		
		或
		
		if expression; then
			command1
		elif expression2; then
			command2
		elif expression2; then
			command3
		fi

4. case判断结构

		case VAR in
		var1) command1 ;;
		var2) command2 ;;
		var3) command3 ;;
		...
		*) command ;;
		esac
		
		其原理为从上到下依次比较VAR和var1、var2、var3的值是否相等。若匹配相等，则执行后面的命令，在无一匹配的情况下，匹配最后的默认*，并执行后面的默认命令。
		
		注意：case判断结构中的var1、var2、var3等值，仅能是常量或正则表达式。