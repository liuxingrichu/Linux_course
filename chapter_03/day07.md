### vim编辑器之多文件 ###
1. 打开
	1. 水平
		1. vim -o test1.txt test2.txt
	2. 垂直
		1. vim -O test1.txt test2.txt
	3. 层次
		1. vim test1.txt test2.txt
2. 切换
	1. 下一个 
		1. :bn		
		2. :bn!
		3. :next
		4. :next!
		5. :n
		6. :n!
	2. 上一个 
		1. :bp
		2. :previous
	3. 直接跳转 :open file
	4. 第一个 :first
	5. 最后一个 :last
	6. 向后跳2个文件 :2n
3. 关闭
	1. 不保存关闭所有
		1. 未修改 :qa
		2. 已修改 :qa!
	2. 保存关闭所有:wqa
4. 差异化比较
	1. vimdiff *
