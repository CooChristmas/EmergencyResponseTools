除了我在登录还有谁在登录？
```
sudo who
```
最近20次登录机器记录
```
sudo lastlog
```
是否有未授权的公钥
```
cat ~/.ssh/authorized_keys
```
在系统最后更改的25个文件
```
sudo find . type f -printf '%T@ @p\n' |sort -n |tail -25 |cut -f2- -d" "
```
开启是否有恶意启动项
```
sudo service --status-all
```
后台是否有监视屏幕的会话
```
sudo ps auxw|grep -i screen|grep -v grep
```
哪些端口正在被监听，哪些ip正在连接
```
sudo netstat -plant && sudo lsof -i
```
在
/etc/reslov.conf有哪些未授权的主机地址
```
sudo cat /etc/hosts && sudo cat /etc/resolv.conf
```
是否在机器上设置了ip转发
```
sudo sysctl -w net.inet.ip.forwarding
```
是否有其他网络适配器开启的隐蔽隧道
```
sudo ifconfig && sudo ip addr
```
是否有恶意进程在后台运行
```
sudo ps auxf
```
那个用户使用了sudo
```
sudo grep sudo /var/log/secure
```
谁尝试登录过机器
```
/var/log/auth.log && /var/log/secure
```

