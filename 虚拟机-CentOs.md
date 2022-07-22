# 虚拟机-CentOs

## 修改CentOs时区

```
yum install ntp
ntpdate us.pool.ntp.org
cp -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
reboot
```

## 查看虚拟机IP

```
ip addr
centos的ip地址是ens33条目中的inet值
使用xshell连接，IP为inet值，端口为22
```

## 安装chrome

* ```
  cd /etc/yun.repos.d
  vim google-chrome.repo  ## 配置下载源;
  ————————————————手动分割————————————————————
  ## 在vim编辑模式添加以下内容;
  [google-chrome]
  name=google-chrome
  baseurl=http://dl.google.com/linux/rpm/stable/$basearch
  enable=1
  gpgcheck=1
  gpgkey=https://dl-ssl.google.com/linux/linux_signing_key.pub
  ```

* ```
  yum -y install google-chrome-stable --nogpgcheck
  ## google-chrome已经安装完毕;
  ```

* ```
  # 创建桌面快捷方式
  ## chrome默认的位置在/usr/share/applications
  方式一:依次点击文件夹，找到chrome后右键复制到桌面;
  方式二：利用命令行;
  cd /usr/share/applications  ## 进入到安装位置;
  cp /usr/share/applications/google-chrome.desktop /home/username/Desktop
  ## username是自己的用户名;
  ```

* ```
  # 复制后的图像化界面如果不是root用户，会有锁，需要添加权限
  cd /home/username/Desktop
  chmod 777 *  ## 修改权限
  ```

* ```
  # 创建linux桌面快捷启动方式启动提示”untrusted application launcher“
  **原因分析：**用户权限的问题，新版本的Gnome桌面快捷方式如果默认是root，则不让启动。
  **解决方案：**把文件权限设置为普通用户权限，启动时使用root密码确认即可解决。
  修改文件权限指令：
  chown test:test /home/test/Desktop/*.desktop  => test为用户名
  ```


## 创建虚拟机，网络适配器选择

* 桥接模式：可以访问互联网，互联网也可以访问你。
* NAT模式：可以访问互联网，互联网不可以访问你。
* 仅主机模式：不可以访问互联网，互联网不可以访问你。

## 防火墙

* 查看防火墙运行状态

  ```
  systemctl status firewalld.service
  ```



## permission denied

* 未使用root账户登录，显示permission denied

## 虚拟机ftp连接不上

* 使用21端口登录，21端口登录不上。使用22端口登录，22端口可以登录。
