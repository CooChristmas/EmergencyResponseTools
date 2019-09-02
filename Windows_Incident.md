# WindowsIncident
我们无论在在做Windows还是Linux安全事件应急，其实一些内置的工具就基本满足，这篇文章我们主要写一下Windows下应急响应
### 注册表排查
```
运行->regedit
```
注册表是一个非常有用的工具，他能告诉我们系统究竟发生了什么，发生的时间以及如何发生的，比如说用户以及他们最后一次使用系统的时间，最近使用过的软件，挂载系统的任何设备，包括可移动驱动器，连接过什么热点，访问过什么文件，都有什么账户，克隆账号有没有，以下列出常用的一些注册表，可以当作知识库来查阅
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
HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\TypedURLs //用户最后访问URl记录
HKEY_LOCAL_MACHINE\System\Services\CurrentControlSet\services\Tcpip\Parameters\Interfaces //判断黑客是否使用来某个特定的IP
HK_Local_Machine\System\ControlSet00x\Enum\USBSTOR //曾经连接过系统的USB设备列表
HKEY_LOCAL_MACHINE\System\MountedDevices //挂载过的设备
```
详细的请参考secist大佬的帖子[点击我进行跳转](https://www.freebuf.com/articles/system/142417.html)


### 资源使用排查
### 网络连接排查
### 服务进程排查
### 共享排查
### 文件排查
### 账号排查
### 计划任务排查
### 自启排查
### 日志排查

