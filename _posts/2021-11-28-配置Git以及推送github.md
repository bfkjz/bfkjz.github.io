---
layout: mypost
title: 配置Git以及推送github
categories: [Git,github]
---  

> 记录使用Git、配置Git，以及推送到github远程仓库  

## 下载安装  

看另外一篇文章 [下载安装Git](https://) 


## 配置Git账户  

可以在 cmd 或者 任意文件夹内，右键 Git Bash Here  
```c  
/* 添加user.name */
git config --global user.name bfkjz  

/*添加user.email */  
git config --global user.email 94xxxxxx2@qq.com  
```    

最好是和github上的一致，这些信息在仓库贡献者上显示  



## 删除Git账户  

```c  
/* 删除user.name */  
git config --global --unset user.name
 
/* 删除user.email */  
git config --global user.email  
```    

## 查看Git配置信息  
```c  
git config --list  
  /* 或者 */
git config -l  
/* 结尾卡在“END”，输入 q  退出 */  
```   
  
  

## 推送github  

1. github创建空白的仓库，不勾选 Add Readme  

1. 进入[token设置页面](https://github.com/settings/tokens)获取token  
    - 点击 Generate new token  
    - Note栏 可以随便命名  
    - Expiration栏 选择过期时间，也可以设置永久不过期  
    - Select scopes栏 只勾选 repo 即可  
    - 下拉到最底，点击绿色按钮 Generate token  
    - 可以看到一串英文密钥，点击双层蓝色方框进行复制。记得保存好，只显示一次，刷新页面后不再显示  
1. 本地创建文件夹，并且命名和远程仓库一致（其实不一致也可以）  
1. 进入文件夹，添加项目文件  
1. 右键 Git Bah Here  

 
```c  

git init    /* 初始化仓库 */  

git add .   /* 添加所有文件到缓冲区 */  
  
git commit -m "注释内容"    /* 添加注释 */  
  
git remote add origin https://tonken@github.com/拥有者/仓库名.git  /* 绑定远程仓库 */  
/* 例：git remote add origin https://ghp_xxxxxxxxxxxxxxxxxxxx@github.com/bfkjz/bfkjz.github.io.git */  
  
git push origin master     /* 推送到master分支 */  
```  
不出意外的话，已经推送成功。目前已知开启全局代理会上传失败，需要关闭全局代理  
    
  

## git remote查看远程仓库信息  
```c  
git remote -v  
```    
## git remote绑定远程仓库  
```c    
/* git remote add 命名 地址 */  
git remote add origin https://ghp_xxxxxxxxxxxxxxxxxxxx@github.com/bfkjz/bfkjz.github.io.git  
```   
## git remote更改命名远程仓库  
```c  
/* git remote rename 旧命名 新命名 */  
git remote rename origin newname  
```  

## git remote删除远程仓库  
```c  
/* git remote remove 命名 */  
git remote remove origin  
```  

## git remote推送远程仓库  
```c   
/* git remote 命名 分支 */  
git push origin master  
```   

## 从远程仓库获取最新版本到本地  
```c    
/* 拉取master分支到newVersion分支 */  
git fetch origin master:newVersion  
```   

## 比较本地的仓库和远程仓库的区别
```c  
/* 拉取master分支到newVersion分支 */  
git diff newVersion  
/* 按 q 退出  */  
```   

## 合并newVerison分支到master分支
```c  
git merge newVersion
```  

## 删除newVerison分支
```c  
git branch -d newVersion  
``` 

