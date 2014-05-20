#在Fedora20上启动sshd服务


##启动SSH服务

使用systemctl命令

	systemctl start sshd.service
或者使用service命令

	service sshd start
	service sshd restart 
	service sshd stop 

##设置系统启动时开启服务
	systemctl enable sshd.service

#开启防火墙22端口
	iptables -A INPUT -p tcp --dport 22 -j ACCEPT

或者将上述参数加入防火墙配置中：
   
	vi /etc/sysconfig/iptables
	-A INPUT -m state --state NEW -m tcp -p tcp --dport 22 -j ACCEPT
保存后重启iptables即可