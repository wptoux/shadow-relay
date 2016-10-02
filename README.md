# shadow-relay

没有什么阻碍是一个搭载 shadowsocks 的 vps 翻不过去的；如果有，那就再来一个！

此命令可以将连接到本台电脑的指定端口的流量转发至目标机器的目标端口，
并接收返回的报文转发至源Ip，
用来转接Shadowsocks再合适不过了。

值得注意的是，此命令重启后需要重新设置。

命令:    
```
relay local_ip local_port dest_ip dest_port
```

其中，
+ local_ip 表示本机想要用来处理流量转发的网上的ip
+ local_port 表示本机接收流量的端口号
+ dest_ip 表示目标机器的ip
+ dest_port 表示目标机器的端口号

主要适用于内网连接外网机器速度较慢，需要添加新的机器作为中转的情况。

## 典型示例：

内网机器 ip 为 ip0，外网为 ip1，中转为 ip2。外网端口为 port1，中转端口为 port2。

### 添加中转之前的设置

内网机器：
+ 目标ip: ip1
+ 目标端口: port1

### 添加中转之后的设置

内网机器：
+ 目标ip: ip2
+ 目标端口: port2

中转机器:
```
relay ip2 port2 ip1 port 1
```



