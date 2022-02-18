使用说明：
需要在ZABBIX agent配置文件中增加以下信息。


UnsafeUserParameters=1
AllowKey=system.run[c:\Windows\System32\cscript.exe /nologo c:\Windows\System32\slmgr.vbs /xpr] 



经测试无法正常使用
