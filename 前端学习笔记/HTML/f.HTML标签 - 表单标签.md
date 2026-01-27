---
theme: condensed-night-purple
---
# HTML标签 - 表单标签

### 什么是表单标签？

表单是一种专门用于收集客户信息的载体。

表单标签格式：

```html
<form>
  <表单元素>
</form>
```

### 什么是表单元素？

> *补充：什么是元素*
>
> -   在HTML中标签/标记/元素都是指HTML中的标签。
> -   例如：`<a>` `a`标签/`a`标记/`a`元素.

表单元素还是HTML中的一些标签，只不过这些标签比较特殊，在浏览器中所有的表单标签都有特殊的外观和默认的功能。

-   `input`标签

    `input`标签有一个`type`属性，这个属性有很多不同的取值，取值的不同就决定了`input`标签的功能和外观。

    -   明文输入框：

        -   格式:
            ```html
            <input type="text">
            ```
        -   可以通过设定`value`属性添加默认值。

    -   暗文输入框：

        -   格式：
            ```html
            <input type=password">
            ```
        -   可以通过设定`value`属性添加默认值。

    -   单选框

        -   格式：
            ```html
            <input type="radio">
            ```
        -   注意点：

            -   默认情况下各单选框之间并不会互斥，要想单选框之间互斥，那么必须给每一个单选框标签都设置一个`name`属性，然后`name`属性必须设置相同的值，只有`name`属性相同的单选框之间才会互斥。
            -   要想让单选框默认选中某一个，那么可以给`input`标签添加一个`checked`属性。相同`name`属性的单选框，只会在其中一个生效。
            -   在HTML中如果属性的取值和属性的名称一样，可以只写一个。但是在开发中最好不要省略取值。

    -   多选框

        -   格式：
            ```html
            <input type="checkbox">
            ```
        -   注意点：`checked`属性会在相同`name`属性的多选框，多个一起生效，会对网页信息提交时产生影响。

    -   按钮

        -   格式：
            ```html
            <input type="button">
            ```
        -   作用：配合`js`完成一些操作。
        -   可以通过指定`value`属性设置按钮的内容。

    -   图片按钮

        -   格式：
            ```html
            <input type="image" src="图片地址">
            ```
        -   作用：配合`js`完成一些操作。
        -   可以通过`src`指定图片地址。

    -   重置按钮

        -   格式：
            ```html
            <input type="reset">
            ```
        -   作用：专门用来清空表单当中数据。
        -   注意点：重置按钮有默认的按钮标题，默认叫“重置”，也可以通过`value`属性进行更改。

    -   提交按钮

        -   格式：
            ```html
            <input type="submit">
            ```
        -   作用：将表单中的数据提交到远程服务器。
        -   注意点：
            -   要想把表单中的数据提交到远程服务器，必须满足(1)告诉表单提交到哪个服务器(2)告诉表单中的哪些数据需要提交。
            -   可以通过`form`标签的`action`属性来告诉表单提交到哪个服务器。
            -   表单中设置了`name`属性的表单元素会提交。

    -   隐藏域

        -   格式：
            ```html
            <input type="hidden">
            ```
        -   作用：用于隐式的收集用户的一些数据，隐藏是不会出现在界面上的。

    -   邮箱输入框：

        -   格式：
            ```html
            <input type="email">
            ```
        -   作用：可以自动校验输入的内容是否符合邮箱的格式。

    -   域名输入框：

        -   格式：
            ```html
            <input type="url">
            ```
        -   作用：可以自动校验输入的内容是否是url地址。

    -   数字输入框：

        -   格式：
            ```html
            <input type="number">
            ```
        -   作用：输入框中只能输入数字，可以点箭头实现加减。

    -   时间选择框：

        -   格式：
            ```html
            <input type="date">
            ```
        -   作用：可以通过日历选择时间。

    -   颜色选择框：

        -   格式：
            ```html
            <input type="color">
            ```
        -   作用：可以通过取色板来选择颜色。

-   `label`标签：

    -   默认情况下文字和输入框是没有关联关系的，也就是说点击文字输入框不会聚焦，如果想点击文字时让对应的输入框聚焦，那么就需要让文字和输入框进行绑定。

    -   要想让输入框和文字绑定在一起，那么我们可以使用`label`标签。

    -   格式：
        1.   将文字用`label`标签包裹起来。
        2.   给输入框添加一个`id`属性。
        3.   在`label`标签中通过`for`属性和输入框中的`id`进行绑定即可。
        ```html
        <label for="输入框id1">文字</label><input type="text" id="输入框id">
        <label for="输入框id2">文字</label><input type="password" id="输入框id2">
        ```
        还可以用`label`标签直接包裹需要绑定的内容。
        ```html
        <label>
          文字<input type="text">
        </lable>
        ```

-   `datalist`标签

    -   可以给输入框绑定待选项。
    -   格式：

        ```html
        <input type="text" list="idName">
        <datalist id="idName">
          <option value="待选项内容"></option>
        </datalist>
        ```
    -   如何给输入框绑定待选列表

        1.   先设置一个输入框。
        2.   搞一个`datalist`列表。
        3.   给`datalist`列表标签添加一个`id`。
        4.   给输入框添加一个`list`属性，将`datalist`的`id`对应的值赋值给`list`属性即可。
        5.   通过`option`标签的`value`属性来设置待选项内容。

    -   由于众多浏览器不支持，故仅做了解即可，后续通过框架实现。

-   `select`标签

    -   作用：用来定义下拉列表。
    -   格式：
        ```html
        <select>
          <optgroup label="这一组数据的标题1">
            <option>列表数据</option>
            <option selected="selected">列表数据</option>
          </optgroup>
          <optgroup label="这一组数据的标题2">
            <option>列表数据</option>
            <option>列表数据</option>
          </optgroup>
        </select>
        ```
    -   注意点：

        -   下拉列表不能输入内容，但是可以直接在列表中选择内容。
        -   可以通过`option`标签添加`selected`属性，来给列表添加默认值。
        -   可以通过给`option`标签包裹一层`optgroup`标签来给下拉列表中的数据分组。

-   `textarea`标签

    -   作用：定义一个多行的输入框。
    -   格式：
        ```html
        <textarea>
        </textarea>
        ```
    -   注意点：

        -   默认情况下输入框可以无限换行。
        -   默认情况下输入框有自己的宽度和高度。
        -   可以通过`cols`和`rows`来制定输入框的宽度和高度，但是虽然指定了列数和行数，但是还是可以无限往下输入。
        -   默认情况下输入框是可以手动拉伸的。

### 案例示例：
```html
<form action="">
    <!--明文输入框-->
    账号：<input type="text"><br><br>
    <!--暗文输入框-->
    密码：<input type="password"><br><br>
    <!--设定默认值-->
    账号：<input type="text" value="wjb">
    密码：<input type="password" value="123123"><br><br>
    <!--单选框-->
    性别：
    <input type="radio" name="gender" checked="checked">男
    <input type="radio" name="gender" checked="checked">女
    <input type="radio" name="gender">保密<br><br>
    国籍：
    <input type="radio" name="country">中国
    <input type="radio" name="country" checked="checked">外国
    <input type="radio" name="country">保密<br><br>
    <!--多选框-->
    爱好：
    <input type="checkbox" name="hobby">篮球
    <input type="checkbox" name="hobby">足球
    <input type="checkbox" name="hobby">棒球
    <input type="checkbox" name="hobby">网球<br><br>
    <!--按钮-->
    <input type="button" value="我是按钮"><br><br>
    <input type="submit"><br><br>
    <input type="image" src="https://pic.616pic.com/ys_bnew_img/00/06/53/zF7Lv0uf54.jpg"><br><br>
    <input type="reset"><br><br>

    邮箱：<input type="email"><br><br>

    <!--输入框待选项-->
    搜索内容：<input type="text" list="idName">
    <datalist id="idName">
        <option value="表单标签的用途？"></option>
    </datalist>
    <br><br>

    <!--下拉选项框-->
    下拉选项框：
    <select name="" id="">
        <optgroup label="">
            <option value="">下拉选项1</option>
            <option value="">下拉选项2</option>
        </optgroup>
    </select>
    <br><br>
    
    <!--多行输入框-->
    多行输入框：
    <textarea cols="11" rows="4">
    </textarea>
</form>
```

**参考链接：**

W3School官方文档：[https://www.w3school.com.cn](https://www.w3school.com.cn/)