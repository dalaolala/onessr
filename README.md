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




安装docker
```
curl -sSL https://get.docker.com/ | sh
service docker restart

docker stop $(docker ps -a -q) 
docker rm $(docker ps -a -q)
docker images
docker rmi <image id>
```

docker一键启动ssr
```
docker run -dt --name ss --restart=always -p 6443:6443 mritd/shadowsocks -s "-s 0.0.0.0 -p 6443 -m chacha20-ietf-poly1305 -k test123" 

```
一键BBR加速
```
wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh"
chmod +x tcp.sh
./tcp.sh
```
