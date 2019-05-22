## 安装vsftpd
```
yum install -y vsftpd
```

## 修改配置文件
```
cd /etc/vsftpd
user_list  # 白名单
ftpusers   # 黑名单
vsftpd.conf # 配置文件
vi vsftpd.conf
以下参数需要修改
anonymous_enable=no # 不允许匿名登录
chroot_local_user=no # 禁止用户跳出宿主目录
```

## 新建用户
```
useradd username -d /usr/local # 新建用户
passwd username # 修改用户密码
```

## 启动服务
```
service vsftpd status # 查看服务状态
service vsftpd start # 启动服务
service vsftpd restart # 重启服务
#netstat -an | grep 21
  tcp    0   0 0.0.0.0:21         0.0.0.0:*          LISTEN 
看到以上信息代表服务已启动
```
## 使用
```
浏览器访问ftp://ip:21  输入上面添加的用户名和密码就可以访问了
如果列表中不显示文件列表
你需要在/home/usernmae/路径下放入文件即可
```

