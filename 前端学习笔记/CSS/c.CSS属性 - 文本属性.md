# CSS属性 - 文本属性

### 文本装饰属性

+ 格式：`text-decoration:underline;`

+ 取值：

  + `underline`：下划线

  + `line-through`：删除线

  + `overline`：上划线

  + `none`：什么都没有，最常见的用途就是用于去掉超链接的下划线。

+ 快捷键：

  + 输入`td` + 按`tab`键：`text-decoration: none;`

  + 输入`tdu` + 按`tab`键 : `text-decoration: underline;`

  + 输入`tdl` + 按`tab`键 : `text-decoration: line-through;`

  + 输入`tdo` + 按`tab`键 : `text-decoration: overline;` 

+ 样式效果：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>文本属性练习</title>
          <style type="text/css">
              .setUnderline {
                  text-decoration: underline;
              }
              .setOverline {
                  text-decoration: overline;
              }
              .setLineThrought {
                  text-decoration: line-through;
              }
          </style>
      </head>
      <body>
          <p class="non">New York</p>
          <p class="setUnderline">New York</p>
          <p class="setLineThrought">New York</p>
          <p class="setOverline">New York</p>
      </body>
  </html>
  ```

  

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-text-decoration.png" alt="text-decoration属性" style="zoom: 33%;" />



二、文本水平对齐的属性

+ 格式：`text-align: center;`

+ 取值：如果文本方向是从左到右，则默认为左对齐；如果文本方向是从右到左，则默认是右对齐。

  + `left`：左。

  + `right`：右。

  + `center`：中。

+ 快捷键：

  + 输入`ta` + 按`tab` 键：`text-align: left;`

  + 输入`tar`+ 按`tab` 键： `text-align: right;`

  + 输入`tac`+ 按`tab`键： `text-align: center;`

+ 样式效果：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>文本属性练习</title>
          <style type="text/css">
              .setCenter {
                  text-align: center;
              }
              .setRight {
                  text-align: right;
              }
          </style>
      </head>
      <body>
          <h1>文本左对齐</h1>
          <p class="non">New York</p>
          <hr>
          <h1>文本居中</h1>
          <p class="setCenter">New York</p>
          <hr>
          <h1>文本右对齐</h1>
          <p class="setRight">New York</p>
      </body>
  </html>
  ```

  ![text-align属性](https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-text-align.png)



### 文本缩进的属性

+ 格式：`text-indent: 2em;`

+ 取值：（均为具体数值 + 单位）

  + 可以以em为单位，一个em代表缩进一个文字的宽度。

  + 可以以px为单位。

+ 快捷键：

  + 输入`ti` + 按`tab`键：`text-indent: ;`

  + 输入`ti2e` + 按`tab`键： `text-indent: 2em;`

+ 样式效果：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>文本属性练习</title>
          <style type="text/css">
              .setTextIndent {
                  text-indent: 2em;
              }
          </style>
      </head>
      <body>
          <p class="non">New York</p>
          <p class="setTextIndent">New York</p>
      </body>
  </html>
  ```

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-text-indent.png" alt="text-indent属性" style="zoom:33%;" />



### 修改文本颜色属性

+ 格式：`color: #ff0000;`

+ 取值：

  + 可以通过英文单词赋值
    + 一般情况下，常见的颜色都有对应的英文单词，英文单词能够表达的颜色是有限制的，也就是说不是所有的颜色都能通过英文单词来做表达。

  + 可以通过`rgb`赋值

    + `rgb`其实就是三原色，`r-red`，`g-green`，`b-blue`。

    + 格式：`rgb(红色, 绿色, 蓝色)`。那么这个格式中的第一个数字就是用来设置三原色的光源元件红色显示的亮度；第二个数字设置三原色的光源元件绿色显示的亮度；第三个数字设置三原色的光源元件蓝色显示的亮度。

    + 这其中的每一个数字的取值是0-255之间，0代表不发光，255代表发光，值越大就越亮。

    + 只要让红色、绿色、蓝色的值都一样就是灰色，而且这个值越小越偏向黑色，值越大越偏向白色。

  + 可以通过`rgba`赋值（CSS3推出）

    + `rgba`中的`rgb`和前面讲解的一样，只不过多了一个`a`。

    + 那么这个`a`代表透明度，取值`0-1`，取值越小越透明。

  + 可以通过十六进制赋值

    + 在前端开发中，通过16进制来表示颜色， 其实本质就是`rgb`，十六进制中是通过每两位表示一个颜色。

    + 例如：`#FFEE00` FF表示`r`， EE表示`g`，00表示`b`。

  + 可以通过十六进制缩写赋值

    + 在CSS中只要十六进制的颜色每两位的值都是一样的就可以简写为一位。

    + 例如：`#FFEE00`  ==> `#FE0`
    + 这里需要注意：如果当前颜色对应的两位数字不一样，就不能简写；如果两位相同的数字不是属于同一个颜色的，也不能简写。

**参考链接：**

W3School官方文档：[https://www.w3school.com.cn](https://www.w3school.com.cn/)