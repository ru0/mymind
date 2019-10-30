
# HACKMIND

在线浏览
https://ru0.github.io/mind/

这是一个很艰难的决定，在自己空余时间做的一个内网渗透相关的脑图，现在决定将其开源。与其在自己的手中烂掉，不如吸引有兴趣的小伙伴参与。

在学习工作中，由于记忆力原因，我一直都想要有一个可随时翻查的渗透手册，不用每次遇到坑就现查资料。一部即查即用手册可以节约大量时间，也能帮助梳理相关知识点，于是就有了ru0's mind,本项目使用freemind编写。自己断断续续坚持写了一些，不过一个人还是心有余而力不足。

在脑图越来越多和详细的时候我发现脑图并不能满足我最初想要的效果，脑图应该像是目录一样的东西，而不是错综复杂的文字。后面如何做，这也是我一直在思考的问题，当然也期待你的加入。

![avatar](https://github.com/ru0/mymind/blob/master/HackMind.png)

@ruo
2019/10/30

## 扩展（寻找域控）

* ### DMZ
	* 提权
	  - WINDOWS
	* 绕过防火墙
	  * 端口转发
	    * lcx
	    * firecat
	    * socat
	    * Fpipe
	    * rtcp.py
	    * netsh
	    * nc
	  * socks代理
	    * 常用工具
	      * ssh
	      * htran
	      * vIDC
	      * sSocks
	    * 辅助工具
	      * ProxyCap
	      * Proxifier
	      * Proxychains
	      * iptables
	  * Web代理
	    * Tunna
	    * reGeorg
	    * reDuh
	  * 修改防火墙配置
	    * 禁用windows防火墙
	* 反弹shell
	  * bash
	  * perl
	  * python
	  * php
	  * java
	  * msf
	* 文件上传下载
	  * webshell
	  * bitsadmin
	  * certutil
	  * wput
	  * wget
	  * aria2c
	  * Powershell
	  * VBS
	  * nc
	  * FTP
	  * Tftp
	  * scp
	  * rsync
	* 横向渗透
	  * 网站代理
	    * Glype
	  * 发现存活主机
	    * Nbtscan
	    * s.exe
	    * nc
	    * Nmap
	    * masscan
	    * 自写脚本
	  * 弱口令扫描
	    * Hydra
	    * Tomcat
	    * Mysql
	  * 欺骗
	    * Responder
* 判断是否是目标域
  * 查看本地ip
  * 查看DNS解析
  * DNS缓存
  * tracert
  * systeminfo
  * net time
  * 敏感信息获取
    * 抓取密码
    * 系统VPN
    * 网络密码
    * 浏览器收藏夹
    * IE代理
    * 浏览器密码
    * putty保存的会话
    * SecureCRT
    * 远程桌面历史记录
    * PLSQL配置文件
    * 查看本地连接
    * windows凭据管理
    * 查看本机ip
    * 开机时间
    * 查看本地路由表
    * hosts文件
    * 翻看目录文件
    * 键盘记录器
    * Linux


## 域

* #### 域控制器
  * 获取域信息
    * 常用工具
       * Daquery
       * Dsget
       * Net group
       * csvde
       * Ldifde
       * ADExplorer
    * 查询域信任关系
       * 术语
       * Nltest
       * Netdom
    * 抓取密码
       * minikatz
       * wce
       * Pwdump
       * GetHashes
       * gsecdump
    * 攻击域控
       * MS14-068
       * SPN
       * GPP组策略偏好
       * Golden Tickets
          * ticketer.py
       * Silver Tickets
       * Pass The Hash
          * wmiexec.py
          * minikatz
          * smbmap.py
          * psexec.py
          * xfreerdp
  * NTDS
    * syskey
    * 拷贝ntds.dit
       * Ntdsutil snapshot
       * vshadow
       * vssown.vbs
    * 导出域hash
      * NTDSDump
      * QuarksPwDump
      * NTDSXTract
      * secretsdump.py
    * 破解hash
      * John the Ripper
      * SAMInside
      * Hashcat
      * Ophcrack
  * DNS服务器
    * Dnscmd

* #### 定位管理员
  * 日志分析
    * userWorkstations
    * Dumpel
    * Wevtutil
    * wecutil
    * Elogdmp
    * Get-EventLog
    * Get-WinEvent
    * logparse
    * evtwalk
  * Powerview
  * PsLoggedon.exe
  * LastLogon
  * PVEFindADUser.exe
  * Query
  * IIS日志
  * 用户登录脚本

## 常用工具

* Net
  * net use
  * net user
  * net session
  * net share
  * net view
* 文件操作
  * 文件查找
  * findstr
  * 压缩/解压文件
  * dir
  * fsutil
  * cacls
  * du.exe
  * del
  * rmdir
  * rd
  * copy
* 命令执行
  * CMSTP
  * Mavinject
  * DiskSshadow
  * sdbinst
* mstsc强制连接
* WMI
  * wmic
  * Get-WmiObject
  * WinRM
  * mof后门
* 计划任务
  * at
  * schtasks
* sc修改服务
* 修改策略
 * secedit
 * auditpol
 * 密码策略
* 其他
  * 查看系统时间
* 微软工具包
 * Windows Server 2003 Service Pack 1 32-bit Support Tools 
 * Remote Server Administration Tools
 * Windows Server 2003 Resource Kit Tools 
 * SubInACL
 * Sysinternals Suite


## 持久化控制

* RAT
  * Cobalt Strike
  * Metasploit
* 后门
  * Shim
  * windows账号克隆
  * ssh
    * openssh
    * tsh
    * 软连接
    * pam
    * 端口复用
  * WEB
    * IIS
      * 后门组件
      * Appcmd.exe
    * tomcat
    * webshell
  * 无文件
    * Userinit
    * wmi定时任务
    * 计划任务