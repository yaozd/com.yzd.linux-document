####V2ray����װ������
```
V2Ray ����ָ��
https://toutyrater.github.io/
V2ray����װ������
https://github.com/v2ray/v2ray-core/releases
```
### -��ǰlinux����CentOS 7

#### ��װ-�Ƽ�ʹ�ñ��ذ�װ
```
��װ��ѹ����ѹ����
yum -y install zip unzip 

wget https://install.direct/go.sh

��װ���ص� v1.13 �汾
./go.sh --version v1.13 --local /root/v2ray-linux-64.zip

���� V2Ray
systemctl start v2ray

systemctl stop v2ray

systemctl restart v2ray
```
#### window�ͷ���ʹ��
```
1.����v2rayN.exe
https://github.com/2dust/v2rayN/releases/tag/2.16
2.v2ray-windows-64.zip
https://github.com/v2ray/v2ray-core/releases
```
####
- [��װ V2Ray �� V2Ray ����ָ��|V2Ray �׻��Ľ̳�](https://toutyrater.github.io/prep/install.html)
- [���ذ�װ �� Project V �ٷ���վ](https://www.v2ray.com/chapter_00/install.html)
- [���㿪ʼ��ʷ�����꾡V2Ray�ͼ�Ľ̳�](https://www.rxblog.xyz/digitalocean-build-v2ray-0-1/)

### -V1:Linux�·�����config.json
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
### -V1:Window�ͻ�������
```
vmess://ew0KICAidiI6ICIyIiwNCiAgInBzIjogInh4IiwNCiAgImFkZCI6ICIxOTIuMTY4LjEuMjM5IiwNCiAgInBvcnQiOiAiNTAwMTUiLA0KICAiaWQiOiAiZjUwMGVjZjUtZTEzNS00OWM2LTljZTItNzhlYjQ5MGQwYWI5IiwNCiAgImFpZCI6ICI2NCIsDQogICJuZXQiOiAidGNwIiwNCiAgInR5cGUiOiAibm9uZSIsDQogICJob3N0IjogIiIsDQogICJwYXRoIjogIiIsDQogICJ0bHMiOiAiIg0KfQ==
```