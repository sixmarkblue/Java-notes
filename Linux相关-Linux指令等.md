

# Linux指令

## 创建目录(绝对路径)

* mkdir -p

## 复制文件

* cp ./当前目录文件  目的目录

## 删除文件

* rm -rf 删除文件（当前目录，直接拼接文件名）

## 显示当前文件目录

* pwd 显示当前文件目录

## 增加用户

* adduser elst  增加elst用户

* passwd chengyi2020  设置密码

  

## 切换用户

* su -elst

## 编辑文件

* vim 编辑文件
* wq 保存退出
* :q退出 不保存退出

## 授权执行命令

* chmod +x bin/elasticsearch 

## 移动到上一级目录

* mv * ../

## 将日志文件三百万行后内容复制到临时文件中

* tail -n +3000000 gateway-test.out > gateway-test.out.tmp

## 将日志文件最后三百万行内容复制到临时文件中

* tail -n 3000000 gateway-test.out > gateway-test.out.tmp

## 临时文件移动覆盖旧文件

* mv gateway-test.out.tmp gateway-test.out

## 清空日志文件

* cat /dev/null > gateway-test.out

## 抓包

* tcpdump -i any -s 0 -w test.cap

## 查看当前Linux系统版本号

```linux
cat /etc/redhat-release
```

## 创建文件

```
cat >> my_default.cnf => 创建my_default.cnf文件
```

## 发版-更新项目

### 启动项目

* ```
  nohup java -jar social.jar >> temp.log 2>&1 &     -> 不覆盖追加输出到temp.log
  ```

* ```
  nohup java -jar social.jar > temp.log 2>&1 &     -> 覆盖输出到temp.log
  ```

### 查看进程

* ```
  ps -ef|grep social  -> 查看带有该字符串的进程
  ```

### 杀进程

* ```
  kill -9 19931  -> 19931-进程id
  ```


## 解压文件

```
解压压缩包到/usr/local/zookeeper目录下
tar -zxvf zookeeper-3.4.6.tar. gz -C /usr/local/zookeeper
```

## mv指令

### 更改文件名字

```
mv apache-zookeeper-3.5.5-bin.tar.gz zookeeper-3.5.5.tar.gz
```

### 移动当前目录下所有文件到指定目录

```
mv ./* /home/kafka
```



# Linux文件颜色的含义

* 绿色文件：可执行文件，可执行程序

* 红色文件：压缩文件或者包文件

* 蓝色文件：目录

* 白色文件：一般性文件，如文本文件，配置文件，源码文件等

* 浅蓝色文件：链接文件，主要是使用in命令建立的文件

* 红色闪烁：表示链接文件有问题

* 黄色：表示设备文件

* 灰色：表示其他文件

