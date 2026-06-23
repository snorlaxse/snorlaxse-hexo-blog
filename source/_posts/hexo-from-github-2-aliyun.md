---
title: hexo-from-github-2-aliyun
date: 2020-03-28 21:49:08
photos: https://cdn.jsdelivr.net/gh/honjun/cdn@1.4/img/banner/links.jpg
tags:
hide_homepage: true
---


## 基础教程
[GitHub+Hexo 搭建个人网站详细教程](https://zhuanlan.zhihu.com/p/26625249)
[Hexo 从 GitHub 到阿里云](https://zhuanlan.zhihu.com/p/58654392)  
[将hexo个人博客部署到个人云服务器--最详细踩坑教程](https://zhuanlan.zhihu.com/p/120743882)

<!--more--> 

## 踩坑指南

### 无法访问

开放80端口 https://developer.aliyun.com/article/738083

重新加载nginx配置文件并启动
nginx -s reload
nginx -s stop
ps -ef | grep nginx


### 经测试hook过程 未成功

```
hint: The 'hooks/post-receive' hook was ignored because it's not set as executable.
hint: You can disable this warning with `git config advice.ignoredHook false`.
hint: The 'hooks/post-update' hook was ignored because it's not set as executable.
hint: You can disable this warning with `git config advice.ignoredHook false`.
To 139.196.185.25:/home/snorlax/git/hexo.git
   888065a..5a2a84e  HEAD -> main
Branch 'main' set up to track remote branch 'main' from 'git@139.196.185.25:/home/snorlax/git/hexo.git'.
INFO  Deploy done: git
```

↑ 解决方案：chmod +x post-receive

```
Counting objects: 100% (15/15), done.
Delta compression using up to 16 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (8/8), 706 bytes | 706.00 KiB/s, done.
Total 8 (delta 4), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (4/4), completed with 4 local objects.
To github.com:snorlaxse/snorlaxse.github.io.git
   00dea05..bcfab84  HEAD -> main
Branch 'main' set up to track remote branch 'main' from 'git@github.com:snorlaxse/snorlaxse.github.io.git'.
On branch main
nothing to commit, working tree clean
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 16 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (8/8), 706 bytes | 706.00 KiB/s, done.
Total 8 (delta 4), reused 0 (delta 0), pack-reused 0
remote: fatal: You are on a branch yet to be born
To 139.196.185.25:/home/snorlax/hexo.git
   00dea05..bcfab84  HEAD -> main
Branch 'main' set up to track remote branch 'main' from 'root@139.196.185.25:/home/snorlax/hexo.git'.
INFO  Deploy done: git
```

↑ 解决方法：
```
#!/bin/sh
git --work-tree=/home/snorlax/snorlaxse.github.io --git-dir=/home/snorlax/hexo.git checkout -f
 ➜  git --work-tree=/home/snorlax/snorlaxse.github.io --git-dir=/home/snorlax/hexo.git checkout main(对应分支名) -f
```

```shell
#!/bin/sh

while read oldrev newrev refname
do
    branch=$(git rev-parse --symbolic --abbrev-ref $refname)
    if [ "origin" = "$branch" ]; then
        git --git-dir=`pwd` --work-tree=/path/to/html reset --hard origin
    fi
done
```

### hexo-asset-image 图片相对路径失效

修改 `package.json` 中的 `"hexo-asset-image": "^1.0.0"`（版本过老） 为 `"hexo-asset-image-for-hexo5": "^2.0.0"`

