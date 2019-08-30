# WindowsIncident
我们无论在在做Windows还是Linux安全事件应急，其实一些内置的工具就基本满足，这篇文章我们主要写一下Windows IR
## IR的顺序
我们在IR过程中，需要隔离或关闭被攻击对系统，但我们在隔离的时候系统的注册表，缓存内容，内存，网络连接状态就会丢失，所以我们建议如下的排查方式
* 注册表，缓存内容
* 内存信息
* 网络连接状态
* 进程运行状态
* 文件及硬盘的情况
* 可移动设备和备份设备信息

对于以上我们如果进行隔离或者关闭系统这些信息就会丢失或者更改

* 系统日期和时间
* 当前运行的进程
* 当前的网络连接
* 目前开放的端口
* 当前登录的账号
### 注册表排查
排查方法：
```
运行->regedit
```
注册表是一个非常有用的工具，他能告诉我们系统究竟发生了什么，发生的时间以及如何发生的，比如说用户以及他们最后一次使用系统的时间，最近使用过的软件，挂载系统的任何设备，包括可移动驱动器，连接过什么热点，访问过什么文件，都有什么账户，克隆账号有没有
```
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Session Manager\KnownDLLs 
HKEY_LOCAL_MACHINE\System\ControlSet001\Control\Session Manager\KnownDLLs
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run //特定用户登录时启动
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\RunOnce 
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\RunServices 
HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\Windows 
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run //查看启动项
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunOnce //只运行一次的启动程序
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunServices 
HKEY_CURRENT_USER\Software\Microsoft\Windows NT\CurrentVersion\Windows 
HKEY_LOCAL_MACHINE\sam\sam\Domains\Account\Users HKEY_LOCAL_MACHINE\sam\sam\Domains\Account\Users\names
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Profiles //我们可以通过这个注册表看出连接过的无线AP
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs //我们可以通过文件扩展来跟踪系统上使用或打开的最新文档
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\WOW //启动遗留应用程序

```
详细的请参考secist大佬的https://www.freebuf.com/articles/system/142417.html


### 资源使用排查
### 网络连接排查
### 服务进程排查
### 共享排查
### 文件排查
### 账号排查
### 计划任务排查
### 自启排查
### 日志排查

