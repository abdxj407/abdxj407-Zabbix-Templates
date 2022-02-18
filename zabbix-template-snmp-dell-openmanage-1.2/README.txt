需要修改默认如下：

1、修改依赖名称

on line 2989 should look like this:

<dependency>
    <name>{HOST.NAME} is unavailable by ICMP</name>
    <expression>{Template ICMP Ping:icmpping.max(#3)}=0</expression\>
</dependency>



2、修改SNMP密钥为变量

I have just found a bug this newly template to be totally functional, on line 2683 replace:

<snmp_community>public</snmp_community>

by this value:

<snmp_community>{$SNMP_COMMUNITY}</snmp_community>


3、修改依赖名称（1好像不用了）
I just had to change the downloaded .xml like below (line 2989) :

<dependency>
<name>Unavailable by ICMP ping</name>
<expression>{Template Module ICMP Ping:icmpping.max(#3)}=0</expression>
</dependency>

4、必须变更的值
for zabbix 5.0LTS you must change
Host is unavailable via ICMP ping {Template ICMP Ping:icmpping[].max(#3)}=0

to
Unavailable by ICMP ping {Template Module ICMP Ping:icmpping.max(#3)}=0 