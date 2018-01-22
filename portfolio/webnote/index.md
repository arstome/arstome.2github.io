---
layout: article
title:  "关于网页常用宽度"
date:   2017-11-30 22:07:50 +0800
categories: notes_tech Jekyll
image:
  teaser: C_SDG goals_icons-individual-RGB-01.jpg
  feature: C_SDG goals_icons-individual-RGB-01.jpg
---
详细的网页宽度设置科普。

网页设计中，宽度的设置，是没有绝对固定的值的，根据我们的需求出发。这里我做个详细的网页宽度设置科普。

网页的宽度主要分两种：
定宽：内容区域宽度固定
自适应：内容区域宽度跟随浏览器变化

## 定宽模式

定宽是我们日常最常见的形式，主流的宽度有 960px / 980px / 1190px / 1210px 等。那么为什么会出现这几个宽度，而不是我们想象中显示器分辨率常见宽如 1024、1280 呢？
1、客户端显示器局限性：
在定义网页宽度时，我们第一件事是考虑我们的受众用的显示器。大家都知道，显示器基本都是从 1024px 起始的，即使今天这个分辨率的显示设备已经很稀有了（虽然ipad也使用这个规格），我们就要根据客观条件考虑自己要支持最低的分辨率。
如为一些特定的企业设计web管理系统，应用的设备统一是 1440px 宽以上的，那么我们就要按这个宽度作为设计的标准开始设计设计稿。
如果要设计一个面向年轻群体的潮牌官网，可能就会为了更好的展示效果放弃低分辨率的用户（主要集中在中老年群体），最低按 1366 宽开始支持。
如果是设计像淘宝这样的要满足所有人的网站，那么就要从最低的 1024 开始支持。
假设我们确定了 1024 宽的支持起点，那就还要再做一件事，确定一个主内容的区域宽出来。在我们使用 Word 的时候，大家都知道我们会给 A4 纸面设置一种参数类型叫页边距，不会让文字内容直接贴在纸张边缘上。
同理，网页主内容的区域小于 1024 宽时，才能使左右产生留白。如知乎最小宽度下左右也会留出间距使内容不会直接贴到浏览器上。
![image](https://raw.githubusercontent.com/arstome/arstome.github.io/master/images/web1.jpg)
在word这些工具中，我们对内容区域的定义是用总宽减去间距宽得出的，如果你要这么设置也不是不行，比如用 1024px 减去两侧各 20px 宽得到 984px 的内容区域。但是，主流的这些分辨率并不是依靠这种方式得到的，在网页设计中，还有个重要的基础知识点——栅格。
通过格线计算公式（ W =（a×n）+（n-1）i ）得到严谨实用的内容宽，  具体的可以看下面简述的回答，不在这边展开讨论：
![image](https://raw.githubusercontent.com/arstome/arstome.github.io/master/images/web2.jpg)
所以，要知道 960px、980px 以及类似淘宝、京东这个级别网站所使用的界面宽，都是经过格线系统的体系推导而出的，而不是觉得某个整数看着比较顺眼所以那么设置，即使你对栅格一点概念都没有，也是可以使用这些宽度的。
最简单的定宽长度设置: <b>宽度 = 支持最小宽度 - 左右留白</b>

## 自适应模式

可能很多人听过，响应式布局，尤其前几年 H5 崛起的时候，很多初级网页设计师都觉得，网页设计以后就应该支持全平台，那些老的定宽规格都应该被淘汰。但是，宽度自适应模式和响应式设计不是完全相等的。
响应式设计，是在多种平台下可以良好显示和运行的一种框架，在不同的宽度下回展现出不同的排版和样式。
![image](https://raw.githubusercontent.com/arstome/arstome.github.io/master/images/web3.jpg)
响应式布局是什么，这里是介绍不完的，可以去下面这个网站了解： http://www.bootcss.com
我不怎么推荐大家去使用响应式设计，因为局限性太大，实际的项目开发时长可能还不如 PC、移动端分别开制作。
而一般自适应宽模式，是让主内容区域可以随画布的拉伸而做调整，让整个浏览器的画布区域被最大化利用，展示更多的文字信息或图像，带来更好的浏览体验（设计得好的情况下）。
![image](https://raw.githubusercontent.com/arstome/arstome.github.io/master/images/web4.jpg)
在这种模式下，使用 1920px 或更大的宽来设计是没问题的。但是，你还需要定义一个最小的宽，再出一版设计，来展示极限情况下的视觉效果。因为很多用户会在操作系统中缩小浏览器的宽度来并排其它窗口。
![image](https://raw.githubusercontent.com/arstome/arstome.github.io/master/images/web5.jpg)
但到了今天和未来，2K、3.5K、4K 显示器越来越普及，设计师是虚要考虑 1080P 以外的显示怎么办的。
![image](https://raw.githubusercontent.com/arstome/arstome.github.io/master/images/web6.jpg)
![image](https://raw.githubusercontent.com/arstome/arstome.github.io/master/images/web7.jpg)
设计自适应宽的界面，可以先选用一个合适的宽度作为基础，如 1440px、1920px 等，给出模块拉伸的方案，然后给出最小宽度效果、超出的应对的措施。
![image](https://raw.githubusercontent.com/arstome/arstome.github.io/master/images/web8.jpg)
要设计出切实可行的方案，是需要设计师完全熟悉 HTM5L+CSS3 和基础 JS 的，还需要考虑过大的宽度适应下配图的清晰度和读取效率问题。空谈自适应和响应式布局绝对是浪费团队时间的做法。

## 结尾

还需要做一些说明的是，即使我们采用了定宽的模式，也可以在特定的模块使用自适应模式进行组合的，常见的就是网页的头部和底部，还有部分带有背景色、图案的模块。如上图天猫的案例。
不要用太大的画布进行设计。否则设计出来的演示稿会没有观赏性，对预览效果大打折扣，比如看下面天猫页面的截图当成演示稿的话，肯定比上方那张大量留白的看起来顺眼多了。
![image](https://raw.githubusercontent.com/arstome/arstome.github.io/master/images/web9.jpg)
结论：
<b>网页设计师的目标就是在浏览器和开发语言的限制下找出合适的设计方案。</b>如果没有把握，请就使用 960/980px 的方案即可。如果要使用更宽的画布，则一定要弄明白各项限制和缘由。
