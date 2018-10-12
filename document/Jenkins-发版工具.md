### [发版工具-Jenkins](http://192.168.1.220:8080)
```
http://192.168.1.220:8080
---
重点！！！！！
Jenkins中的git用户权限（只能拉取代码，不能提交，防止运维误操作）
---
1.测试环境打包：
mvn clean & mvn compile -P test & mvn install -DskipTests
---
1.生产环境打包：
mvn clean & mvn compile -P product & mvn install -DskipTests
 
```
### Jenkins-demo

2-V201810121606
```
#!/bin/bash -l
cd /tmp/data-test/com.jebao.root/com.jebao.root
git checkout dev
git pull
git branch
echo "========================================="
//-2 显示最近2条信息-目前推荐此项
git log -2
echo "========================================="
mvn clean & mvn compile -P test & mvn install -DskipTests
```
1-V201810121302
```
#!/bin/bash -l
cd /tmp/data-test/com.jebao.root/com.jebao.root
git checkout dev
git pull
git branch
//-p 按补丁显示每个更新间的差异 -2 显示最近2条信息
git log -p -2
mvn clean & mvn compile -P test & mvn install -DskipTests
```
### git常用命令
```
git branch
git checkout dev
git pull
get log 查看提交历史
https://blog.csdn.net/wh_19910525/article/details/7468549
```
### git发版分支
- dev-XXX 个人开发分支
- develop 开发分支
- test 测试分支 
- master 生产分支

提交流程
```
个人分支-提交->开发分支-提交->测试分支-提交->生产分支
```
