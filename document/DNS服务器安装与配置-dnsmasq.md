## DNS��������װ������-dnsmasq
```
��DNSmasq�С�͵�����DNS
DNSmasq�Ǹ��ǳ�С�ɵ�dns�����������Խ��С��Χ��dns��ѯ���⣬Ʃ�����������
```
### -��ǰlinux����CentOS 7
### -����DNS�����ַ
```
***.168.1.237

```
### -��ǰDNS����
```
***.168.1.237
/etc/dnsmasqhosts
# ���Ի���
***.168.1.214 m.***.cc
***.168.1.214 www.***.cc
***.168.1.214 api.***.cc
***.168.1.214 nerp.***.cc
***.168.1.214 file1.***.cc
***.168.1.214 apcrm.***.cc
***.168.1.7 static1.***.cc
```
### -��װ������-dnsmasq
```
��װDNS
1.�鿴53�˿��Ƿ�ռ��
netstat -lnpt|grep 53
2.��װdnsmasq
yum -y install
3.����DNS����
systemctl start dnsmasq

---------------------

����DNS
1.����dns�����ļ���
vi /etc/resolv.dnsmasq
2.������ݣ�
nameserver 114.114.114.114 
nameserver 8.8.8.8

3.�½�hosts�����ļ�
vi /etc/dnsmasqhosts

4.��ӽ�������
172.18.160.102 test1.com 
172.18.160.103 test2.com
***.168.1.214 m.***.cc
***.168.1.214 www.***.cc

5.�޸�dnsmasq�����ļ���ʹ�������Զ���������ļ�
vi /etc/dnsmasq.conf

6.�޸�������������

resolv-file=/etc/resolv.dnsmasq 
addn-hosts=/etc/dnsmasqhosts

---------------------
7.������������
systemctl restart dnsmasq
8.��֤�����Ƿ������ɹ�
netstat -ntpl
9.��ӿ�������
systemctl enable  dnsmasq

```
### �ֻ�ʹ�ÿ���ͨ���ȵ�WIFI����ʽ�����������Ի���
```
360������wifi��������3��·�ɴ�ǽ���������ƶ�̨ʽ���������apС���� ��ɫ
360����WiFi3 300M �������� ����·���� ��ɫ
��������޷�wifi���Լ������ȵ㼴�ɡ�
```
### �ο���
- [Docker�dnsmasq](https://blog.csdn.net/litty_123/article/details/68487313?from=singlemessage)
