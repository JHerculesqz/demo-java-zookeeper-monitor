#设计目标#
 
zookeeper的监控运维
	
#实现原理#
##1.Netflix Exhibitor##
	
	(1)设计目标
	(2)如何编译/安装/运行(Standalone&Tomcat)
	(3)Core(Custom集成/远程ConfigServer/备份)
	(4)Features
	(5)RestAPI

<font color="red">测试用例</font>
	
	(1)3个独立的zk进程，部署3个Exhibitor,3个Exhibitor各自控制各自的zk
	- 只有explorer能用
	(2)3个独立的zk进程，部署4个Exhibitor，1个Exhibitor控制另外3个zk
	- Exhibitor必须在一个集群，因此这个用例不通过
	(3)3个zk进程形成集群，部署4个Exhibitor，1个Exhibitor控制另外3个zk
	- Exhibitor必须在一个集群，因此这个用例不通过
	(4)3个zk进程形成集群，部署3个Exhibitor，任意1个Exhibitor控制另外3个zk
	- 成功
	
<font color="red">为了便于操作，zk增加两个bat,Exhibitor增加1个bat</font>
	
	1.server.bat
	cd %~dp0
	%~dp0/zkServer.cmd
	cd %~dp0
	
	2.client.bat
	cd %~dp0
	%~dp0/zkCli.cmd --server 127.0.0.1
	cd %~dp0
	
	startExhibitor.bat
	cd %~dp0
	java -jar exhibitor-1.5.6.jar -c file
	cd %~dp0
	
##2.Zabbix##

	TODO:???	

#reference#
	
	http://www.voidcn.com/blog/Jerome_s/article/p-6176474.html
	https://github.com/soabase/exhibitor