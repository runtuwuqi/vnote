# tcpdump- 抓包常用命令
 #### tcpdump 的- 抓包保存到文件的命令参数是-w xxx.cap

- 抓eth1的包
```
tcpdump -i eth1 -w /tmp/xxx.cap
```
- 抓 192.168.1.123的包
```
tcpdump -i eth1 host 192.168.1.123 -w /tmp/xxx.cap
```
- 抓192.168.1.123的80端口的包
```
tcpdump -i eth1 host 192.168.1.123 and port 80 -w /tmp/xxx.cap
```
- 抓192.168.1.123的icmp的包
```
tcpdump -i eth1 host 192.168.1.123 and icmp -w /tmp/xxx.cap
```
- 抓192.168.1.123的80端口和110和25以外的其他端口的包
```
tcpdump -i eth1 host 192.168.1.123 and ! port 80 and ! port 25 and ! port 110 -w /tmp/xxx.cap
```
- 抓vlan 1的包
```
tcpdump -i eth1 port 80 and vlan 1 -w /tmp/xxx.cap
```
- 抓pppoe的密码
```
tcpdump -i eth1 pppoes -w /tmp/xxx.cap
```

#### 以100m大小分割保存文件， 超过100m另开一个文件 -C 100m

- 抓10000个包后退出 -c 10000

- 后台抓包， 控制台退出也不会影响：
```
nohup tcpdump -i eth1 port 110 -w /tmp/xxx.cap &
```
- 抓下来的文件可以直接用wireshark打开