### RedHat6.5 镜像获取 ###
1. 登录[RedHat官网](https://access.redhat.com/)，注册用户.
2. 通过这个网址进入开发者平台 https://developers.redhat.com/auth/realms/rhd/account/，勾选 Red Hat Developer Program 然后点击保存。
3. [镜像下载](https://access.redhat.com/downloads/content/)

补充知识：

	若收不到验证信息，可以使用QQ、163邮箱进行交替进行验证。

	用163邮箱注册，用QQ邮箱进行验证

### 在windows10上，验证RedHat的ISO镜像 ###
1. 切换到镜像位置
2. 在cmd中，执行certutil -hashfile rhel-server-6.5-x86_64-dvd.iso SHA256

		> certutil -hashfile rhel-server-6.5-x86_64-dvd.iso SHA256
		
		SHA256 的 rhel-server-6.5-x86_64-dvd.iso 哈希:
		a51b90f3dd4585781293ea08adde60eeb9cfa94670943bd99e9c07f13a259539
		CertUtil: -hashfile 命令成功完成。
3. 对照RedHat官网的ISO镜像的SHA256值，验证ISO镜像是否是官网镜像。

补充知识：Windows下使用自带certutil工具校验文件MD5、SHA1、SHA256

	certutil -hashfile xxx MD5
	certutil -hashfile xxx SHA1
	certutil -hashfile xxx SHA256
	xxx表示将验证文件的绝对路径（地址要填对）

[参考资料](https://www.mf8.biz/rhel-dev-license/)
