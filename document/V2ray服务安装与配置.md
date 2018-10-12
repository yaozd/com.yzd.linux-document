####V2ray服务安装与配置
```
V2Ray 配置指南
https://toutyrater.github.io/
V2ray服务安装与配置
https://github.com/v2ray/v2ray-core/releases
```
### -当前linux环境CentOS 7

#### 安装-推荐使用本地安装
```
安装解压、加压工具
yum -y install zip unzip 

wget https://install.direct/go.sh

安装本地的 v1.13 版本
./go.sh --version v1.13 --local /root/v2ray-linux-64.zip

启动 V2Ray
systemctl start v2ray

systemctl stop v2ray

systemctl restart v2ray
```
#### window客服端使用
```
1.下载v2rayN.exe
https://github.com/2dust/v2rayN/releases/tag/2.16
2.v2ray-windows-64.zip
https://github.com/v2ray/v2ray-core/releases
```
####
- [安装 V2Ray · V2Ray 配置指南|V2Ray 白话文教程](https://toutyrater.github.io/prep/install.html)
- [下载安装 · Project V 官方网站](https://www.v2ray.com/chapter_00/install.html)
- [从零开始：史上最详尽V2Ray搭建图文教程](https://www.rxblog.xyz/digitalocean-build-v2ray-0-1/)

### -V1:Linux下服务器config.json
```
{
  "log" : {
    "access": "/var/log/v2ray/access.log",
    "error": "/var/log/v2ray/error.log",
    "loglevel": "warning"
  },
  "inbound": {
    "port": 50015,
    "protocol": "vmess",
    "settings": {
      "clients": [
        {
          "id": "f500ecf5-e135-49c6-9ce2-78eb490d0ab9",
          "level": 1,
          "alterId": 64
        }
      ]
    }
  },
  "outbound": {
    "protocol": "freedom",
    "settings": {}
  },
  "outboundDetour": [
    {
      "protocol": "blackhole",
      "settings": {},
      "tag": "blocked"
    }
  ],
  "routing": {
    "strategy": "rules",
    "settings": {
      "rules": [
        {
          "type": "field",
          "ip": [
            "0.0.0.0/8",
            "10.0.0.0/8",
            "100.64.0.0/10",
            "127.0.0.0/8",
            "169.254.0.0/16",
            "172.16.0.0/12",
            "192.0.0.0/24",
            "192.0.2.0/24",
            "192.168.0.0/16",
            "198.18.0.0/15",
            "198.51.100.0/24",
            "203.0.113.0/24",
            "::1/128",
            "fc00::/7",
            "fe80::/10"
          ],
          "outboundTag": "blocked"
        }
      ]
    }
  }
}

```
### -V1:Window客户端配置
```
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogInh4IiwNCiAgImFkZCI6ICIxOTIuMTY4LjEuMjM5IiwNCiAgInBvcnQiOiAiNTAwMTUiLA0KICAiaWQiOiAiZjUwMGVjZjUtZTEzNS00OWM2LTljZTItNzhlYjQ5MGQwYWI5IiwNCiAgImFpZCI6ICI2NCIsDQogICJuZXQiOiAidGNwIiwNCiAgInR5cGUiOiAibm9uZSIsDQogICJob3N0IjogIiIsDQogICJwYXRoIjogIiIsDQogICJ0bHMiOiAiIg0KfQ==
```