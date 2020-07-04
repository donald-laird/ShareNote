# Github和Gitee同步提交的方法

### 前言

有时候我们需要把项目提交到远程仓库，如GitHub、Gitee(码云)、coding等等，但一个个的提交方式实在是太慢了，而且这繁琐的操作在未来，依旧需要自己手动一个个的进行提交。

那有什么办法可以同时(同步)提交多个仓库呢？

### 方法

1.在项目目录找到`.git`隐藏文件夹，如果在项目目录找不到`.git`隐藏文件夹，文件夹右上角打开`查看`然后找到`隐藏的项目`并勾选即可

2.用记事本打开`config`文件，把Gitee(码云)的仓库地址填进去即可

```bash
[core]
    repositoryformatversion = 0
    filemode = false
    bare = false
    logallrefupdates = true
    symlinks = false
    ignorecase = true
[remote "origin"]
    url = https://gitee.com/lete114/lete114.git
    url = https://github.com/lete114/lete114.github.io.git
    fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
    remote = origin
    merge = refs/heads/master
```



最后重新`push`即可，如果Gitee(码云)仓库有过提交，使用此方法第一次提交请使用`强行提交`，避免报错



```bash
git push -f origin master
```