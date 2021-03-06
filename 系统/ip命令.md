# ip命令安装

#### ip命令和ifconfig命令一样，但是功能更加强大，并旨在取代后者。CentOS 7中默认使用ip命令，不在安装ifconfig。ifconfig命令属于net-tools套件，而ip命令属于iproute套件。

##### 安装
```
yum install iproute -y
```
##### 用法
- 1.设置、查看和删除IP地址：
```
设置IP地址——

ip addr add 192.168.1.1/24 dev eth0

查看IP地址——

ip addr show eth0

删除IP地址——

ip addr del 192.168.1.1 dev eth0
```

- 2.修改路由：
```
查看路由表——

ip route show

查看路由包来自的接口(本地接口)——

ip route get 123.125.114.144

更改默认路由——

ip route add default via 192.168.1.254
```

- 3.显示网络信息：
```
显示网络统计信息——

ip -s link

查看ARP条目——

ip neigh(或neighbour)

监控netlink消息——

ip monitor all
```

- 4.激活或停止网络接口：
```
激活网络接口——

ip link set eth0 up

停止网络接口——

ip link set eth0 down
```