# zabbix3.0
 升级3.0版本，监控tomcat性能。二次开发接入



## zabbix3.0系统版本要求
本项目RPM仅用于Zabbix3.0 For CentOS 6 x64位的安装


## zabbix3.0 新增功能：


* 1、WEB界面重新设计，更友好

* 2、趋势预测
{host:vfs.fs.size[/,free].forecast(1h,,10h)}<=0 
{host:vfs.fs.size[/,free].timeleft(1h,,0)}<=10h 
基于1小时的数据，预测10小时可用空间小于等于0报警

* 3、增加了进程CPU利用率监控item

* 4、性能优化：
History cache优化
Action保存在cache中

* 5、在特定的时间执行任务
如：RAID卡监控可能会造成IO性能下降，只在每天的10：00到11：00（业务低峰期）执行，其它时间不允许执行。

* 6、加密支持、
在Zabbix各组件间(server, proxies, agents and command-line utilities)能够用加密通讯了，需要编译使用 TLS (PolarSSL), GnuTLS or OpenSSL library.

* 7、每个人自定义screens和slide，然后共享给其它人

* 8、命令行强制删除历史数据：
个人觉得该功能还是会对数据库造成压力，还是推荐，禁用 HousekeepingFrequency 对history等表进分区，然后drop分区

* 9、趋势预测功能

预测能力，现在可以通过forecast()和timeleft()触发功能。预测功能会分析历史，并返回一个未来值，并判断这个值是否达到了设定的阈值。可用于计算，触发表达式和通知，以提前行动，避免潜在的问题，而不是等待他们发生后再处置。

* 10、escalator支持多个进程
escalator是负责处理action的进程，在有很多action时，action可能处理不过来，如：配置了报警维护，但报警还是报出去了


## zabbix3.0宝典学学习文档：


- [zabbix-server3.0.3版本环境安装部署](http://blog.yangcvo.me/2016/06/19/%E6%80%A7%E8%83%BD%E7%9B%91%E6%8E%A7/Zabbix/zabbix-server3-0-3%E7%89%88%E6%9C%AC%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85%E9%83%A8%E7%BD%B2/)

- [zabbix3.0实现微信报警](http://blog.yangcvo.me/2016/06/22/%E6%80%A7%E8%83%BD%E7%9B%91%E6%8E%A7/Zabbix/zabbix3-0%E5%AE%9E%E7%8E%B0%E5%BE%AE%E4%BF%A1%E6%8A%A5%E8%AD%A6/)


- zabbix性能监控故障总结 [zabbix性能监控故障总结](http://blog.yangcvo.me/2016/02/07/zabbix-故障总结/)

- zabbix监控MySQL-添加自定义监控项 : [zabbix监控MySQL-添加自定义监控项](http://blog.yangcvo.me/2015/09/29/zabbix监控MySQL-添加自定义监控项/)

- zabbix的ICMP_Ping模版实现对客户端网络状态的监控 : [zabbix的ICMP_Ping模版实现对客户端网络状态的监控](http://blog.yangcvo.me/2015/11/18/zabbix的ICMP-Ping模版实现对客户端网络状态的监控/)

