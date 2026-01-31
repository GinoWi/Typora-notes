# CSS属性 - 边框属性

边框就是环绕在标签宽度和高度周围的线条。**下述topValue代表上边框取值参数，RightValue代表右边框取值参数，BottomValue代表下边框取值参数，LeftValue代表左边取值参数。**

### 边框样式属性

+ 格式：`border-style: {topValue} {RightValue} {BottomValue} {LeftValue};`

+ 取值：（格式中value对应的取值，这里仅仅列了几个常用的取值，其他取值可以参考[w3cschool](https://www.w3school.com.cn/css/css_border.asp)文档）

  + `dotted` - 定义点线边框
  + `dashed` - 定义虚线边框
  + `solid` - 定义实线边框
  + `double` - 双线边框
  + `none` - 定义无边框

+ 渲染样式：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>边框属性练习</title>
          <style type="text/css">
              .setDotted {
                  border-style: dotted;
              }
              .setDashed {
                  border-style: dashed;
              }
              .setSolid {
                  border-style: solid;
              }
              .setDouble {
                  border-style: double;
              }
          </style>
      </head>
      <body>
          <p class="non">无边框</p>
          <p class="setDotted">点线边框</p>
          <p class="setDashed">虚线边框</p>
          <p class="setSolid">实线边框</p>
          <p class="setDouble">双边框</p>
      </body>
  </html>
  ```

  ![CSS-border-style](https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-border-style.png)

### 边框宽度属性

+ 格式：`border-width: {topValue} {RightValue} {BottomValue} {LeftValue};`
+ 取值：具体数值，一定要带单位。



### 边框颜色属性

+ 格式：`border-color: {topValue} {RightValue} {BottomValue} {LeftValue};`
+ 取值：
  + 具体颜色英文名称
  + rgb
  + rgba
  + 十六进制



### 边框属性连写格式

+ 格式：

  ```css
  /*连写（同时设置四条边的边框） --  连写方式（1）*/
  border: {border-width} {border-style} {border-color};
  
  /*连写（方向）-- 连写方式（2）*/
  border-top: {border-width} {border-style} {border-color};
  border-bottom: {border-width} {border-style} {border-color};
  border-left: {border-width} {border-style} {border-color};
  border-right: {border-width} {border-style} {border-color};
  
  /*连写（要素）-- 连写方式（3）*/
  border-width: {topValue} {RightValue} {BottomValue} {LeftValue};
  border-style: {topValue} {RightValue} {BottomValue} {LeftValue};
  border-color: {topValue} {RightValue} {BottomValue} {LeftValue};
  
  /*非连写（方向 + 要素）-- 连写方式（4）*/
  border-top-width: {value};
  border-right-width: {value};
  border-bottom-width: {value};
  border-left-width: {value};
  
  border-top-style: {value};
  border-right-style: {value};
  border-bottom-style: {value};
  border-left-style: {value};
  
  border-top-color: {value};
  border-right-color: {value};
  border-bottom-color: {value};
  border-left-color: {value};
  ```

+ 快捷键：

  + 连写方式（1）：输入`bd` + 按下`Tab`

  + 连写方式（2）：
    + 设置上边框属性：输入`bt` + 按下`Tab`

    + 设置右边框属性：输入`br` + 按下`Tab`

    + 设置下边框属性：输入`bb` + 按下`Tab`

    + 设置左边框属性：输入`bl` + 按下`Tab`

+ 注意点：

  + 连写格式（1）（2）中颜色属性可以省略，省略之后默认就是黑色。
  + 连写格式（1）（2）中样式属性不能省略，省略之后就看不到边框了。
  + 连写格式（1）（2）中宽度可以省略，省略之后还是可以看到边框。
  + 连写格式（3）这三个属性的取值是按照顺时针来复制，也就是按照上右下左来赋值，而不是按照日常生活中的上下左右。
  + 连写格式（3）这三个属性的取值省略的规律：
    + 上右下左 --> 上右下 ：省略左边设置，左边取值和右边一样。
    + 上右下左 --> 上右： 省略下边、左边设置，下边取值和上边一样，左边取值和右边一样。
    + 上右下左 --> 上：省略右边、下边、左边，其他边的取值和上边一样。
  + 根据层叠性，同一个选择器中后面设置的边框属性会覆盖前面的边框属性。
  + 不想要哪一条边框，就将边框设置为`none`。



**参考链接：**

W3School官方文档：[https://www.w3school.com.cn](https://www.w3school.com.cn/)



