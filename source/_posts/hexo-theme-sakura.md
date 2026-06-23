---
title: Hexo-Theme-Sakura
date: 2020-03-30 16:03:10
photos: 
hide_homepage: true
---

## hexo-Github 

* [Mac下使用Hexo+Github搭建个人博客](https://www.jianshu.com/p/e5f95eb990ad)
* [使用Hexo搭建GitHub博客](https://www.jianshu.com/p/cb0750324e26)
* [在github中有哪些好的hexo博客模板？](https://www.zhihu.com/question/39388850)
* [HEXO THE·ME](https://hexothe.me/)
* [Hexo Icarus Theme Settings |Icarus主题设置](https://blog.peiyingchi.com/2017/03/10/hexo-icarus-settings/)
* [使用hexo+icarus搭建个人博客](https://52wufang.com/2020/02/27/%E4%BD%BF%E7%94%A8hexo-icarus%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2/)
* [hexo及icarus主题个性定制](https://angericky.github.io/2018/12/24/icarus%E4%B8%AA%E6%80%A7%E5%AE%9A%E5%88%B6/)
* [littleGreedy](https://littlezero.top/)

<!-- more -->

## Hexo Theme Sakura

* [Hexo-Theme-Sakura LittleGreedy](https://littlezero.top/20181212Hexo-Theme-Sakura/)

hexo-theme-sakura主题 [English document](https://github.com/honjun/hexo-theme-sakura/blob/master/README.md)

基于WordPress主题[Sakura](https://github.com/mashirozx/Sakura/)修改成Hexo的主题。

[demo预览](https://sakura.hojun.cn)

## 1、主题下载安装

[hexo-theme-sakura](https://github.com/honjun/hexo-theme-sakura)建议下载压缩包格式，因为除了主题内容还有些source的配置对新手来说比较太麻烦，直接下载解压就省去这些麻烦咯。

下载好后解压到博客根目录（不是主题目录哦，重复的选择替换）。接着在命令行（cmd、bash）运行`npm i`安装依赖。

## 2、主题配置

### 博客根目录下的_config配置

站点
```yml
# Site
title: 你的站点名
subtitle:
description: 站点简介
keywords:
author: 作者名
language: zh-cn
timezone:
```

部署
```yml
deploy:
  type: git
  repo: 
    github: 你的github仓库地址
    # coding: 你的coding仓库地址
  branch: master
```

备份 （使用hexo b发布备份到远程仓库）
```yml
backup:
  type: git
  message: backup my blog of https://honjun.github.io/
  repository:
    # 你的github仓库地址,备份分支名  （建议新建backup分支）
    github: https://github.com/honjun/honjun.github.io.git,backup
    # coding: https://git.coding.net/hojun/hojun.git,backup

```

### 主题目录下的_config配置

其中标明【改】的是需要修改部门，标明【选】是可改可不改，标明【非】是不用改的部分
```yml
# site name
# 站点名 【改】
prefixName: さくら荘その
siteName: hojun

# favicon and site master avatar
# 站点的favicon和头像 输入图片路径（下面的配置是都是cdn的相对路径，没有cdn请填写完整路径，建议使用jsdeliver搭建一个cdn啦，先去下载我的cdn替换下图片就行了，简单方便~）【改】
favicon: /images/favicon.ico
avatar: /img/custom/avatar.jpg

# 站点url 【改】
url: https://sakura.hojun.cn

# 站点介绍（或者说是个人签名）【改】
description: Live your life with passion! With some drive!

# 站点cdn，没有就为空 【改】  若是cdn为空，一些图片地址就要填完整地址了，比如之前avatar就要填https://cdn.jsdelivr.net/gh/honjun/cdn@1.6/img/custom/avatar.jpg
# [使用jsDeliver+github搭建免费的cdn](https://www.jianshu.com/p/467290ea7e9f)
# [免费CDN：jsDeliver+Github 使用方法](https://zhuanlan.zhihu.com/p/76951130)
cdn: https://cdn.jsdelivr.net/gh/honjun/cdn@1.6

# 开启pjax 【选】
pjax: 1

# 站点首页的公告信息 【改】
notice: hexo-Sakura主题已经开源，目前正在开发中...

# 懒加载的加载中图片 【选】
lazyloadImg: https://cdn.jsdelivr.net/gh/honjun/cdn@1.6/img/loader/orange.progress-bar-stripe-loader.svg

# 站点菜单配置 【选】
menus:
  首页: { path: /, fa: fa-fort-awesome faa-shake }
  归档: { path: /archives, fa: fa-archive faa-shake, submenus: { 
    技术: {path: /categories/技术/, fa: fa-code }, 
    生活: {path: /categories/生活/, fa: fa-file-text-o }, 
    资源: {path: /categories/资源/, fa: fa-cloud-download }, 
    随想: {path: /categories/随想/, fa: fa-commenting-o },
    转载: {path: /categories/转载/, fa: fa-book }
  } }
  清单: { path: javascript:;, fa: fa-list-ul faa-vertical, submenus: { 
    书单: {path: /tags/悦读/, fa: fa-th-list faa-bounce }, 
    番组: {path: /bangumi/, fa: fa-film faa-vertical }, 
    歌单: {path: /music/, fa: fa-headphones },
    图集: {path: /tags/图集/, fa: fa-photo }
  } }
  留言板: { path: /comment/, fa: fa-pencil-square-o faa-tada }
  友人帐: { path: /links/, fa: fa-link faa-shake }
  赞赏: { path: /donate/, fa: fa-heart faa-pulse }
  关于: { path: /, fa: fa-leaf faa-wrench , submenus: { 
    我？: {path: /about/, fa: fa-meetup}, 
    主题: {path: /theme-sakura/, fa: iconfont icon-sakura },
    Lab: {path: /lab/, fa: fa-cogs },
  } }
  客户端: { path: /client/, fa: fa-android faa-vertical }
  RSS: { path: /atom.xml, fa: fa-rss faa-pulse }

# Home page sort type: -1: newer first，1: older first. 【非】
homePageSortType: -1

# Home page article shown number) 【非】
homeArticleShown: 10

# 背景图片 【选】
bgn: 8

# startdash面板 url, title, desc img 【改】
startdash: 
  - {url: /theme-sakura/, title: Sakura, desc: 本站 hexo 主题, img: /img/startdash/sakura.md.png}
  - {url: http://space.bilibili.com/271849279, title: Bilibili, desc: 博主的b站视频, img: /img/startdash/bilibili.jpg}
  - {url: /, title: hojun的万事屋, desc: 技术服务, img: /img/startdash/wangshiwu.jpg}


# your site build time or founded date
# 你的站点建立日期 【改】
siteBuildingTime: 07/17/2018


# 社交按钮(social)  url, img PC端配置 【改】
# [QQ邮箱功能:给我写信!获取代码和连接地址的方法！](https://www.moyublog.com/notes/360.html)
social:
  github: {url: http://github.com/honjun, img: /img/social/github.png}
  sina: {url: http://weibo.com/mashirozx?is_all=1, img: /img/social/sina.png}
  wangyiyun: {url: http://weibo.com/mashirozx?is_all=1, img: /img/social/wangyiyun.png}
  zhihu: {url: http://weibo.com/mashirozx?is_all=1, img: /img/social/zhihu.png}
  email: {url: http://weibo.com/mashirozx?is_all=1, img: /img/social/email.svg}  
  wechat: {url: /#, qrcode: /img/custom/wechat.jpg, img: /img/social/wechat.png}

# 社交按钮(msocial)  url, img 移动端配置 【改】
msocial:
  github: {url: http://github.com/honjun, fa: fa-github, color: 333}
  weibo: {url: http://weibo.com/mashirozx?is_all=1, fa: fa-weibo, color: dd4b39}
  qq: {url: https://wpa.qq.com/msgrd?v=3&uin=954655431&site=qq&menu=yes, fa: fa-qq, color: 25c6fe}

# 赞赏二维码（其中wechatSQ是赞赏单页面的赞赏码图片）【改】
donate:
  alipay: /img/custom/donate/AliPayQR.jpg
  wechat: /img/custom/donate/WeChanQR.jpg
  wechatSQ: /img/custom/donate/WeChanSQ.jpg

# 首页视频地址为https://cdn.jsdelivr.net/gh/honjun/hojun@1.2/Unbroken.mp4，配置如下 【改】
movies:
  url: https://cdn.jsdelivr.net/gh/honjun/hojun@1.2
  # 多个视频用逗号隔开，随机获取。支持的格式目前已知MP4,Flv。其他的可以试下，不保证有用
  name: Unbroken.mp4

# 左下角aplayer播放器配置 主要改id和server这两项，修改详见[aplayer文档] 【改】
aplayer: 
  id: 2660651585
  server: netease
  type: playlist
  fixed: true
  mini: false
  autoplay: false
  loop: all
  order: random
  preload: auto
  volume: 0.7
  mutex: true

# Valine评论配置【改】
valine: true
v_appId: GyC3NzMvd0hT9Yyd2hYIC0MN-gzGzoHsz
v_appKey: mgOpfzbkHYqU92CV4IDlAUHQ
```

## 分类页和标签页配置

### 分类页
![](https://ws3.sinaimg.cn/large/006bYVyvly1g07b0gucy9j31060jih76.jpg)
### 标签页
![](https://wx2.sinaimg.cn/large/006bYVyvly1g07azb2399j31040jgazs.jpg)

配置项在\themes\Sakura\languages\zh-cn.yml里。新增一个分类或标签最好加下哦，当然嫌麻烦可以直接使用一张默认图片（可以改主题或者直接把404图片替换下，征求下意见要不要给这个在配置文件中加个开关，可以issue或群里提出来），现在是没设置的话会使用那种倒立小狗404哦。
```yml
#category
# 按分类名创建
技术:
    #中文标题
    zh: 野生技术协会 
    # 英文标题
    en: Geek – Only for Love
    # 封面图片
    img: https://cdn.jsdelivr.net/gh/honjun/cdn@1.6/img/banner/coding.jpg
生活:
    zh: 生活
    en: live
    img: https://cdn.jsdelivr.net/gh/honjun/cdn@1.6/img/banner/writing.jpg

#tag
# 标签名即是标题
悦读:
    # 封面图片
    img: https://cdn.jsdelivr.net/gh/honjun/cdn@1.6/img/banner/reading.jpg
```

## 单页面封面配置

![](https://ws3.sinaimg.cn/large/006bYVyvly1g07b1pi619j31080jge4u.jpg)
如留言板页面页面，位于source下的comment下，打开index.md如下：
```md
---
title: comment
date: 2018-12-20 23:13:48
keywords: 留言板
description: 
comments: true
# 在这里配置单页面头部图片，自定义替换哦~
photos: https://cdn.jsdelivr.net/gh/honjun/cdn@1.4/img/banner/comment.jpg
---
```


## 单页面配置

### 番组计划页 （请直接在下载后的文件中改，下面的添加了注释可能会有些影响）
![](https://wx2.sinaimg.cn/large/006bYVyvly1g07b2gyx60j31090jjahj.jpg)

```yml
---
layout: bangumi
title: bangumi
comments: false
date: 2019-02-10 21:32:48
keywords:
description:
bangumis:
  # 番组图片
  - img: https://lain.bgm.tv/pic/cover/l/0e/1e/218971_2y351.jpg
  # 番组名
    title: 朝花夕誓——于离别之朝束起约定之花
  # 追番状态 （追番ing/已追完）
    status: 已追完
  # 追番进度
    progress: 100
  # 番剧日文名称
    jp: さよならの朝に約束の花をかざろう
  # 放送时间
    time: 放送时间: 2018-02-24 SUN.
  # 番剧介绍
    desc:  住在远离尘嚣的土地，一边将每天的事情编织成名为希比欧的布，一边静静生活的伊欧夫人民。在15岁左右外表就停止成长，拥有数百年寿命的他们，被称为“离别的一族”，并被视为活着的传说。没有双亲的伊欧夫少女玛奇亚，过着被伙伴包围的平稳日子，却总感觉“孤身一人”。他们的这种日常，一瞬间就崩溃消失。追求伊欧夫的长寿之血，梅萨蒂军乘坐着名为雷纳特的古代兽发动了进攻。在绝望与混乱之中，伊欧夫的第一美女蕾莉亚被梅萨蒂带走，而玛奇亚暗恋的少年克里姆也失踪了。玛奇亚虽然总算逃脱了，却失去了伙伴和归去之地……。
  - img: https://lain.bgm.tv/pic/cover/l/0e/1e/218971_2y351.jpg
    title: 朝花夕誓——于离别之朝束起约定之花
    status: 已追完
    progress: 50
    jp: さよならの朝に約束の花をかざろう
    time: 放送时间: 2018-02-24 SUN.
    desc: 住在远离尘嚣的土地，一边将每天的事情编织成名为希比欧的布，一边静静生活的伊欧夫人民。在15岁左右外表就停止成长，拥有数百年寿命的他们，被称为“离别的一族”，并被视为活着的传说。没有双亲的伊欧夫少女玛奇亚，过着被伙伴包围的平稳日子，却总感觉“孤身一人”。他们的这种日常，一瞬间就崩溃消失。追求伊欧夫的长寿之血，梅萨蒂军乘坐着名为雷纳特的古代兽发动了进攻。在绝望与混乱之中，伊欧夫的第一美女蕾莉亚被梅萨蒂带走，而玛奇亚暗恋的少年克里姆也失踪了。玛奇亚虽然总算逃脱了，却失去了伙伴和归去之地……。
---
```

### 友链页 （请直接在下载后的文件中改，下面的添加了注释可能会有些影响）
![](https://ws3.sinaimg.cn/large/006bYVyvly1g07b39tleej31080jhjv1.jpg)

```yml
---
layout: links
title: links
# 创建日期，可以改下
date: 2018-12-19 23:11:06 
# 图片上的标题，自定义修改
keywords: 友人帐 
description: 
# true/false 开启/关闭评论
comments: true 
# 页面头部图片，自定义修改
photos: https://cdn.jsdelivr.net/gh/honjun/cdn@1.4/img/banner/links.jpg 
# 友链配置
links: 
  # 类型分组
  - group: 个人项目
    # 类型简介
    desc: 充分说明这家伙是条咸鱼 < (￣︶￣)>
    items:
    # 友链链接
    - url: https://shino.cc/fgvf
    # 友链头像
      img: https://cloud.moezx.cc/Picture/svg/landscape/fields.svg
    # 友链站点名
      name: Google
    # 友链介绍  下面雷同
      desc: Google 镜像
    - url: https://shino.cc/fgvf
      img: https://cloud.moezx.cc/Picture/svg/landscape/fields.svg
      name: Google
      desc: Google 镜像
  # 类型分组...
  - group: 小伙伴们
    desc: 欢迎交换友链 ꉂ(ˊᗜˋ)
    items:
    - url: https://shino.cc/fgvf
      img: https://cloud.moezx.cc/Picture/svg/landscape/fields.svg
      name: Google
      desc: Google 镜像
    - url: https://shino.cc/fgvf
      img: https://cloud.moezx.cc/Picture/svg/landscape/fields.svg
      name: Google
      desc: Google 镜像
---
```

## 写文章配置

主题集成了个人插件hexo-tag-bili和hexo-tag-fancybox_img。其中hexo-tag-bili用来在文章或单页面中插入B站外链视频，使用语法如下：
```md
{% bili video_id [page] %}
```
详细使用教程详见[hexo-tag-bili](https://github.com/honjun/hexo-tag-bili/blob/master/README-zh_cn.md)。

hexo-tag-fancybox_img用来在文章或单页面中图片，使用语法如下：
```md
{% fb_img src [caption] %}
```
详细使用教程详见[hexo-tag-fancybox_img](https://github.com/honjun/hexo-tag-fancybox_img/blob/master/README-zh_cn.md)

## DIY


### 修改页脚

`themes/Sakura/layout/_partial/footer.ejs`
```js
<p style="color: #666666;">&copy 2018</p>
```
修改为
```js
<p style="color: #666666;">&copy 20xx</p>
```

#### "运行时长" 显示

`themes/Sakura/layout/_partial/footer.ejs`:
```ejs
<footer>
  <!-- ... -->
  <p style="color: #666666;">&copy 2020 <i class="fa fa-bar-chart" aria-hidden="true"></i> 小站勉强存活中</p>
  <p> 本站已侥幸存活 <span id="run_time"></span></p>
  <!-- ... -->
</footer>

<!-- 网站显示已经运行多久时间 -->
<script>
    function runTime(){
    var d = new Date(),str = '';
    BirthDay=new Date("May 15, 2020");
    today=new Date();
    timeold=(today.getTime()-BirthDay.getTime());
    sectimeold=timeold/1000
    secondsold=Math.floor(sectimeold);
    msPerDay=24*60*60*1000
    msPerYear=365*24*60*60*1000
    e_daysold=timeold/msPerDay
    e_yearsold=timeold/msPerYear
    daysold=Math.floor(e_daysold);
    yearsold=Math.floor(e_yearsold);
    str = daysold+" 天 ";
    str += d.getHours()+' 时 ';
    str  += d.getMinutes()+' 分 ';
    str+= d.getSeconds()+' 秒 ';
    return str;
    }
    setInterval(function(){$('#run_time').html(runTime())},1000);
</script>
```
其中BirthDay是网站起始日期，是要自己改的。
str显示的是运行多少年多少天，根据自己实际情况更改。

* 参考：[网站显示已经运行多久时间](https://www.zh66.club/2019/09/17/%E7%BD%91%E7%AB%99%E6%98%BE%E7%A4%BA%E5%B7%B2%E7%BB%8F%E8%BF%90%E8%A1%8C%E5%A4%9A%E4%B9%85%E6%97%B6%E9%97%B4/) 👈

### post 模板更改

`scaffolds/post.md`

```markdown
---
title: {{ title }}
date: {{ date }}
author: hojun
avatar: https://wx1.sinaimg.cn/large/006bYVyvgy1ftand2qurdj303c03cdfv.jpg
authorLink: hojun.cn
authorAbout: 一个好奇的人
authorDesc: 一个好奇的人
categories: 技术
comments: true
tags: 
keywords: 
description: 
photos: 
---
```
修改为
```markdown
---
title: {{ title }}
date: {{ date }}
author: SnorlaxSE
avatar: 'http://qiniu.snorlax.top/theme/custom/avatar.jpg'
authorLink: 
authorAbout: 元气满满的卡比兽
authorDesc: 元气满满的卡比兽
categories: 
comments: true
tags: 
keywords: 
description: 
photos: https://cdn.jsdelivr.net/gh/honjun/cdn@1.6/img/banner/coding.jpg
---


<!--more-->

```

### menu模板页

例`友人帐: { path: /links/, fa: fa-link faa-shake }`，该模板文件位于`source/links/index.md`  可适当修改.


### submenus 图标

[fontawesome](https://fontawesome.dashgame.com/)

    
以 `code` 为例， 在`fa: `后 写作`fa-code`即可.
```yml
技术: {path: /categories/技术/, fa: fa-code }, 
```

### 歌单

在[网易云音乐网页版](https://music.163.com/#)  找出想要下载无损的歌单，地址栏地址便是歌单地址；
在`source/music/index.md` 修改id

### 鼠标点击爱心效果

在 `themes/Sakura/source/js` 下新建文件 `click-love.js`，在 click-love.js 文件中添加以下代码：
```js
!function(e,t,a){function n(){c(".heart{width: 10px;height: 10px;position: fixed;background: #f00;transform: rotate(45deg);-webkit-transform: rotate(45deg);-moz-transform: rotate(45deg);}.heart:after,.heart:before{content: '';width: inherit;height: inherit;background: inherit;border-radius: 50%;-webkit-border-radius: 500%;-moz-border-radius: 50%;position: fixed;}.heart:after{top: -5px;}.heart:before{left: -5px;}"),o(),r()}function r(){for(var e=0;e<d.length;e++)d[e].alpha<=0?(t.body.removeChild(d[e].el),d.splice(e,1)):(d[e].y--,d[e].scale+=.004,d[e].alpha-=.013,d[e].el.style.cssText="left:"+d[e].x+"px;top:"+d[e].y+"px;opacity:"+d[e].alpha+";transform:scale("+d[e].scale+","+d[e].scale+") rotate(45deg);background:"+d[e].color+";z-index:99999");requestAnimationFrame(r)}function o(){var t="function"==typeof e.onclick&&e.onclick;e.onclick=function(e){t&&t(),i(e)}}function i(e){var a=t.createElement("div");a.className="heart",d.push({el:a,x:e.clientX-5,y:e.clientY-5,scale:1,alpha:1,color:s()}),t.body.appendChild(a)}function c(e){var a=t.createElement("style");a.type="text/css";try{a.appendChild(t.createTextNode(e))}catch(t){a.styleSheet.cssText=e}t.getElementsByTagName("head")[0].appendChild(a)}function s(){return"rgb("+~~(255*Math.random())+","+~~(255*Math.random())+","+~~(255*Math.random())+")"}var d=[];e.requestAnimationFrame=function(){return e.requestAnimationFrame||e.webkitRequestAnimationFrame||e.mozRequestAnimationFrame||e.oRequestAnimationFrame||e.msRequestAnimationFrame||function(e){setTimeout(e,1e3/60)}}(),n()}(window,document);
```
在 `themes/Sakura/layout/layout.ejs` 文件末尾添加以下代码：
```ejs
<!-- 页面点击小红心 -->
<script type="text/javascript" src="/js/click-love.js"></script>
完成以上操作后，当我们点击鼠标的时候就可以看见爱心的特效了
```

### 樱花飘落特效
在 `themes/Sakura/layout/layout.ejs` 文件末尾添加以下代码：
```ejs
<script src="https://cdn.jsdelivr.net/gh/Zevs6/CDN/js/sakura.js"></script>
```
或将该`sakura.js`文件保存至`themes/Sakura/source/js`，在 `themes/Sakura/layout/layout.ejs` 文件末尾添加以下代码：
```ejs
<!-- 樱花飘落特效 -->
<script src="/js/sakura.js"></script>
```
* 参考：[网页中有趣的动态特效（一位瞎折腾的博主）](https://www.zh66.club/2019/09/08/Interesting/)

### 看板娘

将下面两行代码插入layout目录下`layout.ejs`文件的< html>和</ html>`标签内
```ejs
< script src="https://cdn.jsdelivr.net/npm/jquery/dist/jquery.min.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/font-awesome/css/font-awesome.min.css">
```
将下面一行代码插入layout目录下`layout.ejs`文件的< body>和 </ body>标签内；如不需要，注释此行即可
```ejs
< script src="https://cdn.jsdelivr.net/gh/stevenjoezhang/live2d-widget/autoload.js"></script>
```
#### 把模型替换成自定义模型

* 需要自己搭建后端API，参考 https://github.com/fghrsh/live2d_api

### 切换背景

严格意义上来说这个并不算增加，算是恢复，作者在移植这款主题时，只删除了对应的ejs布局文件，并没有删除style.css和js里面相关代码，想要加上这个功能只需要把原作者的相关的div等加上就行。大佬可自行到白猫（原作者）网站查看源代码加上就行。如果是小白或者比较懒得朋友那你只需要按以下几个步骤即可实现这个功能： 

1:找到 /themes/sakura/layout/layout.ejs

在里面加入两行代码代码位置和内容如下（注释下面那两行）：
```ejs
......
......
......
 <!-- 实现换肤功能 -->
  <%- partial('_partial/setdisplay') %> 
  <%- partial('_partial/set', null, {cache: !config.relative_link}) %>
 
</body>
</html>
```

2: 在/themes/sakura/layout/_partial文件夹下面依次新建set.ejs和setdisplay.ejs,其内容分别如下：

set.ejs
```ejs
<div class="changeSkin-gear no-select">
    <div class="keys" id="setbtn"> <span id="open-skinMenu"> 切换主题 | SCHEME TOOL &nbsp;<i
                class="iconfont icon-gear inline-block rotating"></i> </span></div>
</div>
```
setdisplay.ejs
```ejs
<div class="skin-menu no-select" id="mainskin"  style="position: fixed">
    <div class="theme-controls row-container">
        <ul class="menu-list">
            <li id="white-bg"> <i class="fa fa-television" aria-hidden="true"></i></li>
            <li id="sakura-bg"> <i class="iconfont icon-sakura"></i></li>
            <li id="gribs-bg"> <i class="fa fa-slack" aria-hidden="true"></i></li>
            <li id="KAdots-bg"> <i class="iconfont icon-dots"></i></li>
            <li id="totem-bg"> <i class="fa fa-optin-monster" aria-hidden="true"></i></li>
            <li id="pixiv-bg"> <i class="iconfont icon-pixiv"></i></li>
            <li id="bing-bg"> <i class="iconfont icon-bing"></i></li>
            <li id="dark-bg"> <i class="fa fa-moon-o" aria-hidden="true"></i></li>
        </ul>
    </div>
</div>   
<canvas id="night-mode-cover"></canvas>
```

* 参考：[Sakura新手使用教程 ☆☆☆☆☆](https://www.zh66.club/2019/08/31/Sakura%20-%20course/)

### 引入不蒜子访问量和访问人次统计

不蒜子的添加非常非常方便，[不蒜子](http://busuanzi.ibruce.info/)

在`footer.ejs`中的合适位置，看你要显示在哪个地方，添加：
```ejs
<!--这一段是不蒜子的访问量统计代码-->
<!-- <script async src="//dn-lbstatics.qbox.me/busuanzi/2.3/busuanzi.pure.mini.js"></script> -->
<script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
<span id="busuanzi_container_site_pv">本站总访问量<span id="busuanzi_value_site_pv"></span>次 &nbsp;   </span>
<span id="busuanzi_container_site_uv">访客数<span id="busuanzi_value_site_uv"></span>人次</span>
```
就可以了.

### 用七牛云搭建一个属于自己的图床

* [传送门](https://www.zh66.club/2019/09/17/%E7%94%A8%E4%B8%83%E7%89%9B%E4%BA%91%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E5%9B%BE%E5%BA%8A/)


### SEO优化

- [hexo教程:搜索SEO+阅读量统计+访问量统计+评论系统](https://www.zh66.club/2019/09/02/GitHub-Hexo2/)
- [百度站长平台](https://ziyuan.baidu.com/linksubmit/index?)
- [Google Search Console](https://search.google.com/search-console/not-verified?original_url=/search-console/sitemaps?utm_source%3Dwmx%26utm_medium%3Ddeprecation-pane%26utm_content%3Dsitemap-list&original_resource_id)

### demo

在 `_config.yml` 编辑：

```yml
skip_render: 
  - projects/**,    # 自有demo文件
  - baidu_verify_OSA0I3H9AP.html
  - google74357ce561728b1d.html
```

### 开启SSL证书

- [Hexo 博客开启 https (SSL 证书)](https://www.zh66.club/2019/09/05/Hexo%20-https%20(SSL%20)/)

使用全站加密，http 自动跳转到 https：

```shell

listen       80 default_server;
listen       [::]:80 default_server;
server_name  staunchkai.com;
root         /home/hexo;
 
rewrite ^(.*) https://<your site>$1 permanent;   # 添加的语句
```

### 数学公式渲染

- [在 Hexo 中使用 MathJax 渲染数学公式](http://abelsu7.top/2018/10/29/hexo-mathjax/)
- [Hexo 的 Next 主题中渲染 MathJax 数学公式](https://blog.csdn.net/wgshun616/article/details/81019687)

按步骤完成至"解决语义冲突"，编辑 `themes/Sakura/_config.yml`:

```yml
mathjax: 1  # 1 开启
```

在使用数学公式渲染的md文件表头添加`mathjax: true`，如下所示：

```markdown
---
title: {{ title }}
date: {{ date }}
layout: post
author: SnorlaxSE
<!-- ... -->
mathjax: true

---
```

To be continued...

## 扩展阅读

* [梳理基于Hexo搭建博客的原理](https://littlezero.top/20190831what-is-Hexo/)
* [hexo 文档](https://hexo.io/zh-cn/docs/)
* [Hexo Icarus主题配置完全手册](https://littlezero.top/20190811HexoIc/)
