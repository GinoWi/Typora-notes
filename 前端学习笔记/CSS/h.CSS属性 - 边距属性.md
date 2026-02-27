---
attention: 文章结尾有需关联页面的链接，发布到其他地方是需进行替换。
---

# CSS属性 - 边距属性

### 内边距

边框和内容之间的距离就是内边距。

+ 格式：

```css
/* 非连写 */
padding-top: ${padding-top};
padding-right: ${padding-right};
padding-bottom: ${padding-bottom};
padding-left: ${padding-left};

/* 连写 */
padding: ${padding-top} ${padding-right} ${padding-bottom} ${padding-left};
```

+ 渲染样式：

  未设置`padding`属性的渲染效果：

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-nopadding.png" style="zoom:25%;" />

  可以通过开发者工具中的**Computed**面板观察外面红色盒子的样式：

  ![nopadding-computed](https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-nopadding-computed.png)

  从**Computed**面板当中可以看到这个时候的`padding`属性为0。当我们设置`padding`属性后观察一下变化：

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-padding.png" alt="image-20260214102417792" style="zoom:25%;" />

  再通过**Computed**面板观察一下外面红色盒子当前的样式：

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-padding-computed.png" alt="image-20260214102741517" style="zoom: 50%;" />

  这个时候可以看到盒子里面的`padding`属性为30px，此时元素整体的宽高也会变成560px。

  示例代码：

  ```html
  <!DOCTYPE html>
  <html>
      <head>
          <meta charset="utf-8">
          <title>边距属性练习</title>
          <style>
              .outBox {
                  background-color: red;
                  width: 500px;
                  height: 500px;
                	/*这里使用了连写的方式同时设置了，上右下左四个方向的内边距*/
                  padding: 30px;
              }
              .inBox {
                  background-color: green;
                  width: 200px;
                  height: 200px;
              }
          </style>
      </head>
      <body>
          <div class="outBox">
              <div class="inBox"></div>
          </div>
      </body>
  </html>
  ```

  > **补充内容：**
  >
  > **Computed 面板展示的是“计算后的值”**‌：是将影响元素尺寸的所有 CSS 属性（如 `width`、`height`、`padding`、`border`、`margin`）都拆解并显示为最终的、浏览器实际使用的像素值（或其它单位）。
  >
  > **盒模型图是核心可视化工具**‌：在 Computed 面板的底部，通常会有一个‌**可交互的盒模型示意图**‌。这个图从内到外清晰地展示了四个层级：
  >
  > - ‌**内容区 (content)**‌：显示 `width` 和 `height` 的最终计算值。如果这两个值在 CSS 中被设置为 `auto`，这里就会显示 `auto × auto`，表示其尺寸由内容或父容器决定。
  > - ‌**内边距 (padding)**‌：显示四个方向的内边距数值。
  > - ‌**边框 (border)**‌：显示四个方向的边框宽度。
  > - ‌**外边距 (margin)**‌：显示四个方向的外边距数值。
  >
  > **元素宽高**‌：可以通过将 `width` + `padding-left` + `padding-right` + `border-left` + `border-right` 来计算出元素的‌**总宽度**‌（即“布局宽度”或 `offsetWidth`）。同理，可以通过将`height` + `padding-top` + `padding-bottom` + `border-top` + `border-bottom`来计算出‌**总高度**‌。这个“整体大小”就是元素在页面上实际占据的空间。

+ 注意点：

  + 通过上述示例我们可以观察到，给标签设置了内边距，标签的宽度和高度会发生变化（增加内边距的距离）。

  + 连写格式这三个属性的取值省略规律：
    + `${padding-top}` `${padding-right}` `${padding-bottom}` `${padding-left}`  ---> `${padding-top}` `${padding-right}` `${padding-bottom}`  ：省略左内边距的设置，取值和右内边距一样。
    + `${padding-top}` `${padding-right}` `${padding-bottom}` `${padding-left}`  --->  `${padding-top}` `${padding-right}` ： 省略下内边距、左内边距的设置，下内边距取值和上内边距取值一样，左内边距取值和右内边距取值一样。
    + `${padding-top}` `${padding-right}` `${padding-bottom}` `${padding-left}`  ---> `${padding-top}`：省略右内边距、下内边距、左内边距，则被省略的内边距的取值和上内边距的取值一样。

  + 通过上述示例可以发现，内边距也会有背景颜色，同父元素颜色。



### 外边距

标签和标签之间的距离就是外边距。

+ 格式：

```css
/* 非连写 */
margin-top: ${margin-top};
margin-right: ${margin-right};
margin-bottom: ${margin-bottom};
margin-left: ${margin-left};

/* 连写 */
margin: ${margin-top} ${margin-right} ${margin-bottom} ${margin-left};
```

+ 渲染样式：
  + 两元素父子关系：
  
    先设置一个父元素`div`和一个子元素`div`的初始样式：
  
    <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-nomargin.png" alt="nomargin" style="zoom: 33%;" />
  
    然后给子元素设置`margin-top`属性：
  
    <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-margin-1.png" alt="margin-1" style="zoom:33%;" />
  
    可以看到父元素的`margin`属性仍为0
  
    <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-margin-computed-2.png" alt="margin-computed" style="zoom:50%;" />
  
    可以观察到子元素的`margin`属性为30px
  
    <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-margin-computed-1.png" alt="margin-computed" style="zoom:50%;" />
  
    可以观察到，如果设置了`margin-top: 30px;`属性，父元素会一同被顶下来。
  
    我们可以通过给父元素设置`border`属性，来先观察当下需要了解的`margin`属性：
  
    <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-margin-2.png" alt="margin-2" style="zoom: 33%;" />
  
    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8">
            <title>边距属性练习</title>
            <style>
                .outBox {
                    background-color: red;
                    width: 500px;
                    height: 500px;
                    border: 1px solid #000;
                }
                .inBox {
                    background-color: green;
                    width: 200px;
                    height: 200px;
                    margin: 30px;
                }
            </style>
        </head>
        <body>
            <div class="outBox">
                <div class="inBox"></div>
            </div>
        </body>
    </html>
    ```
  
  + 两元素为兄弟关系：
  
    这里就不再做对比，直接展示设置`margin`属性后的效果：
  
    <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-margin-3.png" alt="margin-brother" style="zoom: 33%;" />
  
    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8">
            <title>边距属性练习</title>
            <style>
                .box1 {
                    background-color: red;
                    width: 100px;
                    height: 100px;
                }
                .box2 {
                    background-color: green;
                    width: 100px;
                    height: 100px;
                    margin: 30px;
                }
            </style>
        </head>
        <body>
            <div class="box1"></div>
            <div class="box2"></div>
        </body>
    </html>
    ```

+ 注意点：

  + 连写格式取值省略时的规律：

    + `${margin-top}` `${margin-right}` `${margin-bottom}` `${margin-left}` --->  `${margin-top}` `${margin-right}` `${margin-bottom}`：省略对左边距的指定，左边距的取值和右边距一样。

    + `${margin-top}` `${margin-right}` `${margin-bottom}` `${margin-left}`  --->  `${margin-top}` `${margin-right}`： 省略下边距、左边距的指定，下边距取值同上边句一样，左边距取值同右边距一样。

    + `${margin-top}` `${margin-right}` `${margin-bottom}` `${margin-left}` ---> `${margin-top}`：省略右边距、下边距、左边距的指定，被省略的边距的取值同上边距一样。


  + 外边距的那一部分是没有背景颜色的。


  + 在默认布局的垂直方向上，默认情况下外边距是不会叠加的，会出现合并显现，原则上是谁设定的外边距比较大就听谁的。

  + 在默认布局的水平方向上，默认情况下外边距是会叠加的，不会进行合并。



### 外边距合并

外边距合并的现象简单来说就是当两个垂直方向的外边距相遇，会形成一个外边距，此外边距大小为两个边距中的最大值（如果两者相等则取其中一个）。

外边距合并的三种情况：

+ 两元素为相邻的兄弟关系：

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-merge-margin-1.png" alt="image-20260224150323247" style="zoom: 67%;" />

+ 两元素为父子关系：

  这里引用MDN文档的解释：

  > 如果没有设定边框（border）、内边距（padding）、行级（inline）内容，也没有创建区块格式化上下文或间隙来分隔块级元素的上边距（margin-top）与其内一个或多个子代块级元素的上边距（margin-top）；或者没有设定边框、内边距、行级内容、高度（height）或最小高度（min-height）来分隔块级元素的下边距（margin-bottom）与其内部的一个或多个后代后代块元素的下边距（margin-bottom），则会出现这些外边距的折叠，重叠部分最终会溢出到父代元素的外面。

  也就是说合并后的外边距大小是取父元素及其内**首个/最后一个**子代块级元素的上边距/下边距的较大值，但是最终的渲染结果都会是“溢出”到父元素面的外边距。

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-merge-margin-2.png" alt="image-20260224155323022" style="zoom: 33%;" />

+ 空元素的外边距合并：

  如果块级元素没有设定边框、内边距、行级内容、高度来分隔块级元素的上边距（margin-top）及其下边距（margin-bottom），则会出现其上下外边距的折叠。

  <img src="https://picgo-storage-typora.oss-cn-shanghai.aliyuncs.com/CSS-merge-margin-3.png" alt="image-20260224160810735" style="zoom:33%;" />

注意点：

- 上述情况的组合会产生更复杂的（超过两个外边距的）外边距折叠。
- 即使某一外边距为 0，这些规则仍然适用。因此就算父元素的外边距是 0，第一个或最后一个子元素的外边距仍然会（根据上述规则）“溢出”到父元素的外面。
- 如果包含负边距，折叠后的外边距的值为最大的正边距与最小（绝对值最大）的负边距的和。
- 如果所有的外边距都为负值，折叠后的外边距的值为最小（绝对值最大）的负边距的值。这一规则适用于相邻元素和嵌套元素。
- 外边距折叠仅与垂直方向有关。

解决外边距折叠的方法：

在说明解决外边距折叠之前，先说明一个概念：区块格式化上下文（Block Formatting Context，BFC），这部分为布局方式里面的内容，可以配合那篇一起看。（**链接。。。**）

> **区块格式化上下文（Block Formatting Context，BFC）**
>
> BFC（Block Formatting Context，块级格式化上下文）是CSS视觉格式化模型中的核心概念，它定义了块级盒子的布局环境。会形成一个独立的渲染区域，内部元素的布局不受外部影响，同时外部元素也不会干扰其内部布局。
>
> 触发条件：
>
> + 文档的根元素（`<html>`）。
> + 浮动元素（即 `float` 值不为 `none` 的元素）。
> + 绝对定位元素（`position` 值为 `absolute` 或 `fixed` 的元素）。
> + 行内块元素（具有 `display: inline-block` 的元素）。
> + 表格单元格（具有 `display: table-cell`（HTML 表格单元格默认值）的元素）。
> + 表格标题（具有 `display: table-caption`)（HTML 表格标题默认值）的元素）。
> + 匿名表格单元格元素，由包括 `display: table`（HTML 表格默认值）、`table-row`（表格行默认值）、`table-row-group`（表格体默认值）、`table-header-group`（表格头部默认值）、`table-footer-group`（表格尾部默认值）的元素隐式创建，或 `inline-table`。
> + 具有 `display: flow-root`的元素。
> + 弹性项（具有 `display: flex`或`inline-flex` 元素的直接子元素），如果它们本身既不是弹性、网格也不是表格容器。
> + 网格项（具有 `display: grid`或`inline-grid` 元素的直接子元素），如果它们本身既不是弹性、网格也不是表格容器。
> + `overflow` 不为 `visible` 或 `paint` 的区块元素。
> + 具有 `contain: layout`、`content` 或 `paint` 的元素。
> + 多列容器（`column-count`或`column-width`) 值不为 `auto`，且含有 `column-count: 1` 的元素）。
> + 具有 `column-span: all`的元素，即使该元素没有包裹在一个多列容器中。
>
> 主要应用场景：
>
> + 解决外边距合并问题
> + 清除浮动影响

+ 可以通过触发BFC来解决外边距合并的问题
+ 可以通过设置`padding`、`border`属性来解决



**参考资料：**

W3School官方文档：[https://www.w3school.com.cn](https://www.w3school.com.cn/)

MDN官方文档：https://developer.mozilla.org
