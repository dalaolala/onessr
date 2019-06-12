# onessr

```
wget https://raw.githubusercontent.com/dalaolala/onessr/master/ssr.sh && bash ssr.sh
```

**给指定的iptables端口放行

#vi /etc/sysconfig/iptables#编辑防火墙配置文件，开放3306端口

添加配置：-A INPUT -p tcp -m state --state NEW -m tcp --dport 3306 -j ACCEPT

#systemctl restart iptables.service 
#最后重启防火墙使配置生效

#systemctl enable iptables.service 
#设置防火墙开机启动
