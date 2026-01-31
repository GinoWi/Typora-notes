# CSS属性 - 文字相关属性

### 规定文字样式属性

+ 格式：`font-style: italic;`

+ 取值：
  + `normal`：正常的，默认取值
  + `italic`：倾斜

+ 快捷键：
  + 输入`fs` +按 `tab`键：`font-style: italic;`
  + 输入`fsn` +按 `tab`键：`font-style: normal;`

+ 样式效果：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>字体属性练习</title>
          <style type="text/css">
              .setItalic {
                  font-style: italic;
              }
          </style>
      </head>
      <body>
          <p class="non">纽约</p>
          <p class="setItalic">纽约</p>
      </body>
  </html>
  ```

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-font-style.png" alt="font-style" style="zoom: 33%;" />



### 规定文字粗细属性

+ 格式：`font-weight: bold;`

+ 取值：
  + 单词：
    + `bold`：加粗
    + `bolder`：比加粗还要粗
    + `lighter`：细线，默认取值
  + 数值：100～900之间整百的数字
  
+ 快捷键：
  + 输入`fw` + 按`tab`键：`font-weight: ;`
  + 输入`fwb` + 按`tab`键：`font-weight: bold;`
  + 输入`fwl` + 按`tab`键：`font-weight: lighter;`
  + 输入`fwbr` + 按`tab`键：`font-weight: bolder;`
  
+ 样式效果：
  
  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>字体属性练习</title>
          <style type="text/css">
              .setBold {
                  font-weight: bold;
              }
              .setBolder {
                  font-weight: bolder;
              }
              .setLighter {
                  font-weight: lighter;
              }
              .setNumber {
                  font-weight: 300;
              }
          </style>
      </head>
      <body>
          <p class="non">纽约</p>
          <p class="setBold">纽约</p>
          <p class="setBolder">纽约</p>
          <p class="setLighter">纽约</p>
          <p class="setNumber">纽约</p>
      </body>
  </html>
  ```
  
  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-font-weight.png" alt="font-weight" style="zoom: 33%;" />

> ***补充内容：***
>
> 在CSS中，`font-weight: bold` 和 `font-weight: bolder` 在视觉上看起来相同，主要原因在于‌**字体的字重（weight）是离散的，而非连续的**‌，并且浏览器会进行‌**最接近的匹配**‌。
>
> 具体来说，有以下几点原因：
>
> - ‌**`bold` 是一个绝对值，对应数字 700**‌。它表示使用字体设计中预设的“粗体”字重版本。
> - ‌**`bolder` 是一个相对值**‌，它表示“比父元素的字重更粗”。如果父元素的字重是 `normal`（400），那么 `bolder` 会将字重设置为 `bold`（700）。但如果父元素已经是 `bold`（700），`bolder` 会尝试设置为下一个更粗的字重（如 800 或 900）。
> - ‌**关键限制在于字体本身**‌：并非所有字体都提供从 100 到 900 的完整字重系列。许多常见字体（如系统默认字体）只提供 `normal`（400）和 `bold`（700）两种字重。当浏览器遇到 `bolder`（如 800 或 900）时，如果该字体没有更粗的版本，浏览器就会‌**回退到可用的最粗字重**‌，也就是 `bold`（700）。
> - ‌**因此，当父元素已经是 `bold` 时，`bolder` 无法显示更粗的效果**‌，因为它没有更粗的字体可用，最终显示效果与 `bold` 完全一致。
>
> 简而言之，`bold` 和 `bolder` 的语义不同（一个是绝对粗体，一个是相对更粗），但在实际显示中，由于字体字重的限制，`bolder` 往往无法实现比 `bold` 更粗的效果，导致两者看起来一模一样。‌
>
> 如果希望看到 `bolder` 的真实效果，需要使用支持更多字重的字体（如 Google Fonts 中的许多现代字体），并在父元素字重为 `normal` 时应用 `bolder`。



### 规定文字大小属性

+ 格式：`font-size: 30px;`

+ 单位：px（pixel） 像素

+ 注意点：通过`font-size`设置大小一定要带单位，也就是一定要写px。

+ 快捷键：输入`fz` + 按`tab`键：`font-size: ;`

+ 样式效果：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>字体属性练习</title>
          <style type="text/css">
              .set30 {
                  font-size: 30px;
              }
          </style>
      </head>
      <body>
          <p class="non">纽约</p>
          <p class="set30">纽约</p>
      </body>
  </html>
  ```

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-font-size.png" alt="font-size" style="zoom: 33%;" />



### 规定文字字体属性

+ 格式：`font-family: ;`

+ 注意点：
  + 如果取值是中文，需要用双引号或者单引号包裹。
  + 设置的字体必须是用户电脑已经安装的字体。
  
+ 快捷键：输入`ff` + 按`tab`键：`font-family: ;`

+ 样式效果：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>字体属性练习</title>
          <style type="text/css">
              .setArial {
                  font-family:'Arial';
              }
          </style>
      </head>
      <body>
          <p class="non">New York</p>
          <p class="setArial">New York</p>
      </body>
  </html>
  ```

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-font-family.png" alt="font-family属性" style="zoom:33%;" />

> ***补充内容：***
>
> + 如果设置字体不存在，那么系统会使用默认的字体来显示（宋体）。
> + 如果设置的字体不存在，而我们又不想用默认的字体来显示怎么办？
>   + 可以字体设置备选方案，格式：`font-family: "字体1", "备选方案1", "备选方案2"...;`
> + 如果想给中文和英文分别单独设置字体，怎么办？
>   + 但凡是中文字体，里面都包含了英文，但凡是英文字体里面没有包含中文。也就是说中文字体可以处理英文，英文字体处理不了中文。
>   + 格式：`font-family: "英文字体", "中文字体";`
>   + 如果想给界面中的英文单独设置字体，英文字体就必须写在中文字体的前面。
> + 在开发过程中，最常见的字体有以下几个：
>   + 中文：宋体、黑体、微软雅黑
>   + 英文：Times New Roman、Arial
> + 并不是名称是英文，就一定是英文字体，因为中文字体都有自己的英文名称，所以是不是中文字体，主要是看能不能处理中文。比如：宋体的英文名称就是SimSun；黑体的英文名称SimHei；微软雅黑的英文名称Microsoft YaHei。



### 文字属性简写：

+ 简写格式：`font: {style} {weight} {size} {family};` 例如：`font: italic bold 10px "楷体";`

+ 快捷键：输入`f` + 按下`Tab`键

+ 注意点：
  + 在这种缩写格式中，`weight`属性可以省略不写。
  + 在这种缩写格式中，`style`属性和`weight`属性位置可以交换。
  + 在这种缩写格式中，`size`属性不能省略，`family`属性不能省略。
  + `size`属性和`family`属性的位置是不能随便乱放的，`size`属性一定要写在`family`属性前面，`size`属性和`family`属性必须写在所有属性的最后。



**参考链接：**

W3School官方文档：[https://www.w3school.com.cn](https://www.w3school.com.cn/)
