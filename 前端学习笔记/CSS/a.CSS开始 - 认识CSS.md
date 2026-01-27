# CSS开始 - 认识CSS

### 我们为什么要使用CSS来设置网页样式？

接下来从两个方面来进行阐述：



一、通过标签来修改样式的缺点：

1. 需要记忆哪些标签有哪些属性，如果该标签没有这个属性，那么设置了也没有效果。

2. 当我们需求变更的时候，我们需要修改大量代码才能满足现有的需求。

3. HTML只有一个作用就是用来添加语义。



二、通过CSS来修改样式有什么好处？

1. 不用记忆哪些属性属于哪个标签。
2. 当需求变更时我们不需要修改大量的代码就可以满足需求。
3. 在前端开发中CSS只有一个作用，就是用来修改样式。



### CSS固定格式：

```html
<style type="text/css">
		选择器 {
				属性名称：属性对应的值；
		}
</style>
```

注意点：

+ `style`标签必须写在`head`标签的开始标签和结束标签之间（也就是必须和`title`标签是兄弟关系）。
+ `style`标签中的`type`属性其实可以不用写，默认就是`type="text/css"`。
+ 设置样式时必须按照固定的格式来设置，`属性名称: 属性值;`，其中分号不能省略。



### CSS体验：

接下来可以通过两种不同方式设置样式进行对比，我们可以先尝试通过设置标签的属性来修改文本样式：

```html
<!--通过html标签的属性修改样式-->
<!DOCTYPE html>
<html> 
    <head>
        <meta charset="utf-8">
        <title>体验CSS</title>
    </head>
    <body>
        <h1 align="center">
            <font face="微软雅黑" color="red" size="5">静夜思</font>
        </h1>
        <p align="center">
            <font face="微软雅黑" color="green">床前明月光</font>
        </p>
        <p align="center">
            <font face="微软雅黑" color="green">疑是地上霜</font>
        </p>
        <p align="center">
            <font face="微软雅黑" color="green">举头望明月</font>
        </p>
        <p align="center">
            <font face="微软雅黑" color="green">低头思故乡</font>
        </p>
    </body>
</html>
```

接下来再通过CSS来设置文本样式：

```html
<!DOCTYPE html>
<html> 
    <head>
        <meta charset="utf-8">
        <title>体验CSS</title>
        <style type="text/css">
            h1 {
                text-align: center;
                color: red;
                font-family: "微软雅黑";
            }
            p {
                text-align: center;
                color: green;
                font-size: 20px;
                font-family: "微软雅黑";
            }
        </style>
    </head>
    <body>
        <h1>静夜思</h1>
        <p>床前明月光</p>
        <p>疑是地上霜</p>
        <p>举头望明月</p>
        <p>低头思故乡</p>
    </body>
</html>
```

通过上述两种样式修改方式的对比，可以更加直观的感受到两者的差别和优劣。



**参考链接：**

W3School官方文档：[https://www.w3school.com.cn](https://www.w3school.com.cn/)
