**onessr**

```
wget https://raw.githubusercontent.com/dalaolala/onessr/master/ssr.sh && bash ssr.sh
```

**给指定的iptables端口放行**

编辑防火墙配置文件，开放端口
```
vi /etc/sysconfig/iptables
```

添加配置：
```
-A INPUT -p tcp -m state --state NEW -m tcp --dport 8888 -j ACCEPT
```

最后重启防火墙使配置生效
```
systemctl restart iptables.service 
```
设置防火墙开机启动
```
systemctl enable iptables.service 
```

