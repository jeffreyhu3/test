# gogs-custom
## 安装
- 添加git用户
```
adduser --disabled-login git
```
- 解压安装包
```
tar -xzvf /opt/gogs_0.12.3_linux_amd64.tar.gz -C /opt/
```
- 修改gogs.service(可参考repo文件systemd/gogs.service)
```
cp /opt/gogs/scripts/systemd/gogs.service /etc/systemd/system/gogs.service
```
- Enable/start gogs.service
```
systemctl enable gogs.service
systemctl start gogs.service
systemctl stop gogs.service
systemctl status gogs.service
```
- 浏览器打开[http://git.lehome.top:3000/install](http://git.lehome.top:3000/install) 进行相关设置。可参考conf/app.ini


## 卸载
- Stop/disable gogs.service
```
systemctl stop gogs.service
systemctl disable gogs.service
rm -rf /etc/systemd/system/gogs.service
``` 
- 删除git用户和用户目录
```
userdel --remove git
```
- 删除安装目录文件
```
rm -rf /opt/gogs
```
