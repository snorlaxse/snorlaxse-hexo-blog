---
title: hexo theme ocean
date: 2022-04-12 16:03:13
tags:
photos: https://cdn.jsdelivr.net/gh/snorlaxse/jsDeliver/cover/gundam00.jpg
---


传送门：
[Github  hexo-theme-ocean](https://github.com/zhwangart/hexo-theme-ocean)
[Ocean 中文文档](https://zhwangart.com/2018/11/30/Ocean/)
[关于 Ocean 使用中的问题](https://zhwangart.com/2019/07/02/Ocean-Issues/)

<!-- more -->

#### 主页视频前置蒙版不透明度  
`themes/ocean/source/css/_partial/ocean.styl` 中
`.video-overlay`   `background-color rgba(178, 191, 204, .6)` → `  background-color rgba(178, 191, 204, .3)`


#### 相册功能
```
albums: [
        ["1", "https://cdn.jsdelivr.net/gh/honjun/cdn@1.4/img/banner/about.jpg"],	# 线上链接
        ["2", "gallery/00.jpg"],		# 本地路径
        ["3", "gallery/01.jpg"],
        ["4", "gallery/02.jpg"],
        ]
```

#### 鼠标样式

于`themes/ocean/source/css/style.styl` 开头 添加
```styl
//  普通指针样式  // 可于`https://zhutix.com/tag/cursors/`挑选样式
body
  cursor url(https://cdn.jsdelivr.net/gh/snorlaxse/jsDeliver/theme/cursor/ComixCursors-White/Comix_White_Pointer.cur),default

// 链接指针样式
a
  &:hover
    cursor url(https://cdn.jsdelivr.net/gh/snorlaxse/jsDeliver/theme/cursor/ComixCursors-White/Comix_White_Link.cur),pointer
```

#### cdn

[使用jsDeliver+github搭建免费的cdn](https://www.jianshu.com/p/467290ea7e9f)
[免费CDN：jsDeliver+Github 使用方法](https://zhuanlan.zhihu.com/p/76951130)

```
![](https://cdn.jsdelivr.net/gh/snorlaxse/jsDeliver/cover/gundam00.jpg)
```

#### 侧边栏自动隐藏

于`themes\ocean\source\css_partial\layou.styl`
```
// Media Query
@media (min-width: 768px)
  .jumbotron
    margin-bottom 6rem

  .content
    margin-right aside-width

  .sidebar
    right 0
    background-color white

  .navbar-toggle
    display none
```
删除相关控制样式的css, 最终修改为:
```
// Media Query
@media (min-width: 768px)
  // .jumbotron
  //   margin-bottom 6rem

  // .content
  //   margin-right aside-width

  .sidebar
    // right 0
    background-color white

  // .navbar-toggle
  //   display none

```
PS：可于`themes/ocean/source/css/_variables.styl` 调整侧边栏宽度 `aside-width`


#### 部署自定义静态HTML

将相应项目文件夹 放置于 `source`下
于`_config.yml`中修改：
```
# 跳过文件夹下所有子文件夹和文件
skip_render: 
  - "文件夹名/**    # ex. "- demo/**/*"
```

#### b站外链

安装插件
```
npm install hexo-tag-bili --save
```

在md文件中编辑：
```html
<div 
     style="position: relative; width: 100%; height: 0; padding-bottom: 75%;">
    <iframe 
            src="//player.bilibili.com/player.html?aid=43224979&bvid=BV1ob411S7gM&cid=75780544&page=1"
            scrolling="no" 
            border="0" 
            frameborder="no" 
            framespacing="0" 
            allowfullscreen="true" 
            style="position: absolute; width: 100%;height: 100%; left: 0; top: 0;"> 
    </iframe>
</div>
```