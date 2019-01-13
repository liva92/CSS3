# css3菜单动画

标签： CSS动画 animation

---

1、案例使用了图标字体，可以用css设置文本阴影等效果;

2、在下面的示例中,只展示每个例子动画样式（浏览器的前缀已存在源文件中）。
### [Example 1][1]
用hover鼠标悬停，更改字体大小和颜色。

### [Example 2][2]
定义了两个动画 moveFromBottom 和 moveFromTop：

 - moveFromBottom：将相应的元素放入 y 轴的200% 开始, 不透明度为0。然后, 将动画到原点设置为 0%,实现从下往上推送的效果：
```
@keyframes moveFromBottom {
    from {
        opacity: 0;
        transform: translateY(200%);
    }
    to {
        opacity: 1;
        transform: translateY(0%);
    }
}
```
 - moveFromTop:使用相同的原则从顶部移动元素:
```
@keyframes moveFromTop {
    from {
        opacity: 0;
        transform: translateY(-200%);
    }
    to {
        opacity: 1;
        transform: translateY(0%);
    }
}
```
### [Example 3][3]
在本例中, 除了更改悬停时的背景和文本颜色，还通过transform属性和放大图标的字体来完成图标的旋转和放大：
```
.ca-menu li:hover{
    background-color: #000;
}
.ca-menu li:hover .ca-icon{
    color: #f900b0;
    font-size: 120px;
    opacity: 0.2;
    left: -20px;
    transform: rotate(20deg);
}
.ca-menu li:hover .ca-main{
    color: #f900b0;
    opacity: 0.8;
}
.ca-menu li:hover .ca-sub{
    color: #fff;
    opacity: 0.8;
}
```
### [Example 4][4]
示例对菜单使用了浮动布局，图标将被放置在项目中心的上半部分，内容包装将放置在项目的下半部分。悬停时, 从顶部滑动并模糊图标,   从底部滑动内容项，更改背景色:
```
.ca-menu li:hover{
    background-color: #fff;
}
.ca-menu li:hover .ca-icon{
    text-shadow: 0px 0px 20px #c5e4f4;
    color: transparent;
    animation: moveFromTop 400ms ease;
}
.ca-menu li:hover .ca-main{
    color: #000;
    animation: moveFromTop 300ms ease;
}
.ca-menu li:hover .ca-sub{
    color: #000;
    animation: moveFromBottom 500ms ease;
}
```
当图标的颜色设置为透明并为其设置具有大量模糊性的文本阴影时, 图标的模糊就会发生。动画原理与前面的相同, 但顶部动画改为translateY：-300%。
### [Example 5][5]
本示例中, 从左侧滑动图标, 从右侧滑动标题, 从底部滑动次要标题
```
@keyframes moveFromLeft{
    from {
        transform: translateX(-100%);
    }
    to {
        transform: translateX(0%);
    }
}
```
### [Example 6][6]
本例从左侧滑动并旋转标题:
```
@keyframes moveFromLeftRotate{
    from {
        transform: translateX(-100%) rotate(-90deg);
    }
    to {
        transform: translateX(0%) rotate(0deg);
    }
}
```
### [Example 7][7]
辅助标题和图标从底部滑入, 而主标题从小到大增加:
```
.ca-menu li:hover .ca-main{
    color: #ff2020;
    animation: smallToBig 300ms ease;
}

@keyframes smallToBig{
    from {
        transform: scale(0.1);
    }
    to {
        transform: scale(1);
    }
}
```
### [Example 8][8]
在本例中,悬停时放大整个列表项，其中 id = #heart 的特殊图标， 设置为从小到大无限交替的动画，实现可爱的心跳效果：
```
.ca-menu li:hover .ca-icon#heart{
    animation: smallToBig 900ms alternate infinite ease;
}
```
### [Example 9][9]
在本例中,悬停时项目旋转 360度, 主标题消失, 辅助项目出现 (其不透明度最初设置为 0)：
```
.ca-menu li:hover{
    background: #f7f7f7;
    border-color: #fff;
    transform: rotate(360deg);
}
.ca-menu li:hover .ca-main{
    display: none;
}
.ca-menu li:hover .ca-sub{
    opacity: 0.8;
}
```
### [Example 10][10]
在上一个示例中, 设置列表项的左边距为-48px。使其重叠。悬停时, 缩放并增加 z-index:
```
.ca-menu li:hover{
    border-color: #333;
    z-index: 999;
    transform: scale(1.1);
}
```


  [1]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index.html
  [2]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index2.html
  [3]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index3.html
  [4]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index4.html
  [5]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index5.html
  [6]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index6.html
  [7]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index7.html
  [8]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index8.html
  [9]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index9.html
  [10]: https://github.com/liva92/CSS3/blob/master/CSS3_menu_demo/index10.html