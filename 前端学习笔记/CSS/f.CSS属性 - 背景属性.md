# CSS属性 - 背景属性

### 如何设置标签的背景颜色

+ 在CSS中有一个`background-color`属性，就是专门用来设置标签的背景颜色的。

+ 取值：

  - 具体颜色单词

  - rgb

  - rgba

  - 十六进制
  
+ 渲染效果：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>背景属性练习</title>
          <style type="text/css">
              div {
                  width: 50px;
                  height: 50px;
              }
              .setEnName {
                  background-color: yellow;
              }
              .setRgb {
                  background-color: rgb(255, 0, 0);
              }
              .setRgba {
                  background-color: rgba(0, 0, 255, 0.9);
              }
              .setHex {
                  background-color: #ff00ff;
              }
          </style>
      </head>
      <body>
          <div class="setEnName"></div>
          <br>
          <div class="setRgb"></div>
          <br>
          <div class="setRgba"></div>
          <br>
          <div class="setHex"></div>
      </body>
  </html>
  ```
  
  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-background-color.png" alt="背景颜色设置" style="zoom:33%;" />

### 如何设置背景图片

+ 在CSS中有一个`background-image`属性，就是专门用来设置背景图片的。

+ 注意点：
  + 图片的地址必须放在`url()`中，可以是本地图片地址，也可以是网页图片地址。
  + 如果图片的大小没有标签的大小大，会自动在水平和垂直方向平铺。
  + 如果网页上出现图片，那么浏览器会再次发送请求，获取图片。
  
+ 渲染效果：
  
  我的原始图片是这个：
  
  ![CSS-background-image-source](https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-background-image-source-1.png)
  
  这个图片的大小是519 × 500像素的大小，接下来用这个图片作为`body`标签的背景图片。
  
  ![CSS-background-image.png](https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-background-image.png)

​	我们可以通过上图看到，由于图片的大小没有标签的大小大，故自动在水平和垂直方向上平铺。



### 如何控制背景图片是否平铺

+ 在上面我们阐述了如何设置背景图片，但是默认背景图片是在标签内平铺的，如果我们想控制背景图片是否在标签内平铺展示，那么在CSS中有一个`background-repeat`属性，就是专门用来控制背景图片的平铺方式。

+ 取值：
  + `repeat`：默认，在水平和垂直方向都需要平铺
  + `no-repeat`：在水平和垂直方向都不平铺
  + `repeat-x`：在水平方向平铺
  + `repeat-y`：在垂直方向平铺

+ 应用场景：
  + 可以通过背景图片的平铺来降低图片的大小，加快网页访问的速度。

+ 注意点：

  + 同一个标签可以同时设置背景颜色和背景图片，如果颜色和图片同时存在，那么图片会覆盖颜色。

+ 渲染效果：

  这里素材图片是大小200×200的方块：

  ![background-repeat-source](https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-background-repeat-source-1.png)

  接下来我们可以通过在不同的`div`盒子中设置背景图片不同的平铺方式，可以得到如下的效果（这里对网页进行了缩小，非真正图片大小）。

  ![background-repeat](https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-background-repeat.png)

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>背景属性练习</title>
          <style type="text/css">
              * {
                  margin: 0;
                  padding: 0;
              }
              div {
                  width: 600px;
                  height: 300px;
                  background-image: url(img/bg2.jpg);
              }
              .setNoRepeat {
                  background-repeat: no-repeat;
                  margin-top: 50px;
              }
              .setRepeatX {
                  background-repeat: repeat-x;
                  margin-top:50px;
              }
              .setRepeatY {
                  background-repeat: repeat-y;
                  margin-top:50px;
              }
          </style>
      </head>
      <body>
          <div class="non"></div>
          <div class="setNoRepeat"></div>
          <div class="setRepeatX"></div>
          <div class="setRepeatY"></div>
      </body>
  </html>
  ```



### 如何设置背景图片的位置

+ 在CSS中有一个叫做`background-position`属性，就是专门用于控制背景图片的位置。

+ 取值：

  + 具体的方位名词
    + 水平方向：`left`、`center`、`right`
    + 垂直方向：`top`、`center`、`bottom`
  + 具体的像素
    + 一定要写单位
    + 可以写负值，垂直方向像素值越大越靠下，水平方向像素值越大越靠右。

+ 格式：

  ```css
  background-position: 水平方向 垂直方向;
  ```

+ 应用场景：

  + 可以解决背景图片不同分辨率展示异常问题。如果通过`img`标签展示图片，可能无法适配浏览器宽度，浏览器下方会显示滚动条，但是通过背景图片展示，会根据浏览器宽度截取图片。



### 背景关联方式

+ 默认情况下背景图片会随着滚动条的滚动而滚动，如果不想让背景图片随着滚动条的滚动而滚动，那么我们就可以修改背景图片和滚动条的关联方式。在CSS中有一个`background-attachment`的属性这个属性就是专门用于修改背景图片关联方式的。

+ 格式：

  ```css
  background-attachment: scroll;
  ```

+ 取值：

  + `scroll`：默认值，会随着滚动条的滚动而滚动。
  + `fixed`： 不会随着滚动条的滚动而滚动。



### 背景属性缩写

+ 背景属性缩写格式：

  ```css
  background：背景颜色 背景图片 平铺方式 关联方式 定位方式;
  ```

+ 快捷键：输入`bg` + 按下`Tab`键

+ 注意点：

  + `background`属性中，任何一个属性都可以被省略。



> **补充内容：**
>
> 背景图片和插入图片的区别
>
> + 背景图片仅仅是一个装饰，不会占用位置；插入图片会占用位置。
>
> + 背景图片有定位属性，所以可以很方便的控制图片的位置；插入图片没有定位属性，所以控制图片的位置不太方便。
>
> + 插入图片的语义比背景图片语义强，所以在开发过程中如果图片想要被搜索引擎收录，那么推荐使用插入图片。



**参考链接：**

W3School官方文档：[https://www.w3school.com.cn](https://www.w3school.com.cn/)
