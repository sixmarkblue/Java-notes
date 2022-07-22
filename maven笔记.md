## maven笔记

## 网上jar包安装到本地maven仓库

```
mvn install:install-file -Dfile=E:/ojdbc8.jar（网上下载jar包存放路径） -DgroupId=com.oracle -DartifactId=ojdbc8 -Dversion=12.2.0.1 -Dpackaging=jar
```

