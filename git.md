### git同步本地文件到github

* git bash

* ```
  git config --global user.name "sixmarkblue"
  git config --global user.email "1938941711@qq.com"
  ssh-keygen -t rsa -C "1938941711@qq.com"   // 生成ssh key 密钥
  c://users/sixmarkblue/.ssh/id_rsa.pub中密钥放到github中配置，add new ssh_key
  ssh -T git@github.com // 命令来检测SSH key是否配置成功
  
  cd d:/java笔记
  git init // 初始化，生成.git文件
  git add . // 将目前文件夹所有文件加到git仓库
  git commit -m "提交注释"     // commit
  git remote add origin https://github.com/sixmarkblue/Java-notes.git  // 关联github仓库地址
  git push -u origin master // 上传本地代码
  ```

* git remote -v  // 查看远程origin地址

* git remote remove origin // 删除现有的origin地址

* git remote add origin  // 添加新的origin地址

* 

* git config --global http.postBuffer 524288000    // 将本地 `http.postBuffer` 数值调整到GitHub服务对应的单次上传大小配置500MB

* ```text
  # 查看当前的Git配置
  git config --list
  ```

* git log // 显示commit 讯息
* git status // 显示讯息





* git config --global --unset https.proxy