# HTML标签 - marquee标签

什么事marquee标签？

跑马灯效果，内容从右至左滚动。

格式：

```html
<marquee>
  内容
</marquee>
```

属性：

+ direction
  + 作用：设置滚动方向。
  + 值：right、up、down、left（默认）
+ scrollamount
  + 作用：设置内容滚动速度，值越大越快。
+ loop
  + 作用：设置滚动次数，默认-1，也就是无限滚动。
+ behavior
  + 作用：设置滚动类型。
  + 属性值：slide（设置滚动到边界就不再滚动，不会出边界消失），alternate（滚到边界弹回，来回滚动）

注意点：

+ marquee标签不是W3C推荐的标签，在W3C官方文档中也无法查询这个标签，但是各大浏览器对这个标签的支持非常好。