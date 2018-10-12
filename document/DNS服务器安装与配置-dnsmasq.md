## DNS服务器安装与配置-dnsmasq
```
用DNSmasq搭建小型的内网DNS
DNSmasq是个非常小巧的dns服务器，可以解决小范围的dns查询问题，譬如机房内网。
```
### -当前linux环境CentOS 7
### -内网DNS服务地址
```
***.168.1.237

```
### -当前DNS配置
```
***.168.1.237
/etc/dnsmasqhosts
# 测试环境
***.168.1.214 m.***.cc
***.168.1.214 www.***.cc
***.168.1.214 api.***.cc
***.168.1.214 nerp.***.cc
***.168.1.214 file1.***.cc
***.168.1.214 apcrm.***.cc
***.168.1.7 static1.***.cc
```
### -安装与配置-dnsmasq
```
安装DNS
1.查看53端口是否被占用
netstat -lnpt|grep 53
2.安装dnsmasq
yum -y install
3.启动DNS服务
systemctl start dnsmasq

---------------------

配置DNS
1.创建dns配置文件：
vi /etc/resolv.dnsmasq
2.添加内容：
nameserver 114.114.114.114 
nameserver 8.8.8.8

3.新建hosts配置文件
vi /etc/dnsmasqhosts

4.添加解析规则
172.18.160.102 test1.com 
172.18.160.103 test2.com
***.168.1.214 m.***.cc
***.168.1.214 www.***.cc

5.修改dnsmasq配置文件，使用我们自定义的配置文件
vi /etc/dnsmasq.conf

6.修改下述两个配置

resolv-file=/etc/resolv.dnsmasq 
addn-hosts=/etc/dnsmasqhosts

---------------------
7.重新启动服务
systemctl restart dnsmasq
8.验证服务是否启动成功
netstat -ntpl
9.添加开机启动
systemctl enable  dnsmasq

```
### 手机使用可以通过热点WIFI的形式访问内网测试环境
```
360°随身wifi无线网卡3代路由穿墙无限迷你移动台式发射接收器ap小网卡 黑色
360随身WiFi3 300M 无线网卡 迷你路由器 黑色
或电脑有无法wifi的自己创建热点即可。
```
### 参考：
- [Docker搭建dnsmasq](https://blog.csdn.net/litty_123/article/details/68487313?from=singlemessage)
