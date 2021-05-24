# Samba的安装与使用



samba是一种网络共享服务，可以通过网络访问我们指定的文件夹。



## 第一步：下载Samba

```
sudo apt-get install samba
```



## 第二步：修改Samba配置文件

```
sudo vim /etc/samba/smb.conf
```

添加如下内容

```
[ubuntu samba]
    comment =arm ubuntu samba dir
    path = /home/samba
    available = yes
    browseable = yes
    public = yes
    writable = yes
    create mask = 0755
    security = share
    force user = root
    force group = root
```



```
[ubuntu samba]
    comment =arm ubuntu samba dir       #说明
    path = /home/samba                  #共享的samba目录，需要真实存在
    available = yes                     #允许访问
    browseable = yes                    #可以浏览
    public = yes                        #公开
    writable = yes                      #可写
    create mask = 0755                  #当外部创建新文件时的权限
    security = share                    #共享模式
    force user = root                   #在外部添加新文件时，文件的所有者
    force group = root                  #在外部添加新文件时，文件的所在组
```



## 第三步：重启Samba

```
sudo service smbd restart

```



## 第四步：在Windows中访问Samba

```
//192.168.1.179
#192.168.1.179 是虚拟机ubuntu的IP
```









