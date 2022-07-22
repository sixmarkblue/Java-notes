# NGINX

## 负载均衡

### 热备

如果你有2台服务器，当一台服务器发生事故时，才启用第二台服务器给提供服务。服务器处理请求的顺序：AAAAAA突然A挂啦，BBBBBBBBBBBBBB.....

```
upstream mysvr { 
    server 127.0.0.1:7878; 
    server 192.168.10.121:3333 backup;  #热备     
}
```

### 轮询

nginx默认就是轮询其权重都默认为1，服务器处理请求的顺序：ABABABABAB....

```
upstream mysvr { 
    server 127.0.0.1:7878;
    server 192.168.10.121:3333;       
}
```

### 加权轮询

跟据配置的权重的大小而分发给不同服务器不同数量的请求。如果不设置，则默认为1。下面服务器的请求顺序为：ABBABBABBABBABB....

```
upstream mysvr { 
    server 127.0.0.1:7878 weight=1;
    server 192.168.10.121:3333 weight=2;
}
```

### ip_hash

nginx会让相同的客户端ip请求相同的服务器。

```
upstream mysvr { 
    server 127.0.0.1:7878; 
    server 192.168.10.121:3333;
    ip_hash;
}
```

![image-20220106173137074](D:\develop\笔记\NGINX.assets\image-20220106173137074-16414615121381.png)