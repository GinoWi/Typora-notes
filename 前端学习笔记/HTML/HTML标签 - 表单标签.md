# HTML标签 - 表单标签

### 什么是表单？

表单就是专门用来收集用户信息的。

表单格式：

```html
<form>
	<表单元素>
</form>
```



### 什么是表单元素？

什么是元素

+ 在HTML中标签/标记/元素都是指HTML中的标签。
+ 例如：`<a>` a标签/a标记/a元素
+ 表单元素其实还是HTML中的一些标签，只不过这些标签比较特殊，在浏览器中所有的表单标签都有特殊的外观和默认的功能。



### 表单元素

+ input标签

  + input标签有一个type属性，这个属性有很多类型的取值，取值的不同就决定了input标签的功能和外观。
  + 明文输入框：
    + 格式:`<input type=text">`
    + 可以通过设定value属性添加默认值
  + 暗文输入框：
    + 格式：`<input type=password">`
    + 可以通过设定value属性添加默认值
  + 单选框
    + 格式：`<input type="radio">`
    + 注意点：
      + 默认情况下单选框不会互斥，要想单选框互斥那么必须给每一个单选框标签都设置一个name属性，然后name属性还必须设置相同的值。
      + 要想让单选框默认选中某一个框子，那么可以给input标签添加一个checked属性。相同name属性的单选框，只会在其中一个生效。
      + 在HTML中如果属性的取值和属性的名称一样，可以只写一个。但是在HTML中必须写上取值，所以在企业开发中我们推荐大家不要省略取值。
  + 多选框
    + 格式：`<input type="checkbox">`
    + checked属性会在相同name属性的多选框，多个一起生效。
  + 按钮
    + 格式：`<input type="button">`  
    + 作用：配合js完成一些操作。
    + 可以通过指定value属性设置按钮的内容。
  + 图片按钮
    + 格式：`<input type="image" src="图片地址">`
    + 作用：配合js完成一些操作。
    + 可以通过src指定图片地址。
  + 重置按钮
    + 格式：`<input type="reset">`
    + 作用：专门用来清空表单当中数据。
    + 注意点：重置按钮有默认的按钮标题，默认叫做重置。也可以通过value属性进行更改。
  + 提交按钮
    + 格式：`<input type="submit">`
    + 作用：将表单中的数据提交到远程服务器。
    + 注意点：
      + 要想把表单中的数据提交到远程服务器，必须满足1.告诉表单提交到哪个服务器2.告诉表单中的哪些数据需要提交。
      + 可以通过form标签的action属性来告诉表单提交到哪个服务器。
      + 表单中设置了name属性的表单元素会提交。
  + 隐藏域
    + 格式：`<input type="hidden">`
    + 作用：用于隐式的收集用户的一些数据，隐藏是不会出现在界面上的。
  + 邮箱输入框：
    + 格式：`<input type="email">`
    + 作用：可以自动校验输入的内容是否符合邮箱的格式。
  + 域名输入框：
    + 格式：`<input type="url">`
    + 作用：可以自动校验输入的内容是否是url地址。
  + 数字输入框：
    + 格式：`<input type="number">`
    + 作用：输入框中只能输入数字，可以点箭头实现加减
  + 时间选择框：
    + 格式：`<input type="date">`
    + 作用：可以通过日历选择时间
  + 颜色选择框：
    + 格式：`<input type="color">`
    + 作用：可以通过取色板来选择颜色。

+ label标签：

  + 默认情况下文字和输入框是没有关联关系的，也就是说点击文字输入框不会聚焦，如果想点击文字时让对应的输入框聚焦，那么就需要让文字和输入框进行绑定

  + 要想让输入框和文字绑定在一起，那么我们可以使用label标签。

  + 格式：

    ```html
    <label for="输入框id1">文字</label><input type="text" id="输入框id">
    <label for="输入框id2">文字</label><input type="password" id="输入框id2">
    ```

    + 将文字利用label标签包裹起来。
    + 给输入框添加一个id属性
    + 在label标签中通过for属性和输入框中的id进行绑定即可
    + 还可以用label标签直接包裹需要绑定的内容

    ```html
    <label>
    	文字<input type="text">
    </lable>
    ```

+ datalist标签

  + 可以给输入框绑定待选项

  + 格式：

    ```html
    <input type="text" list="idName">
    <datalist id="idName">
    	<option>待选项内容</option>
    </datalist>
    ```

  + 如何给输入框绑定待选列表

    + 搞一个输入框
    + 搞一个datalist列表
    + 给datalist列表标签添加一个id
    + 给输入框添加一个list属性，将datalist的id对应的值赋值给list属性即可。

  + 由于众多浏览器不支持，故仅做了解即可，后续通过框架实现。

+ select标签

  + 作用：用来定义下拉列表

  + 格式：

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

  + 注意点：

    + 下拉列表不能输入内容，但是可以直接在列表中选择内容。
    + 可以通过option标签添加selected属性，来给列表添加默认值。
    + 可以通过给option标签包裹一层optgroup标签来给下拉列表中的数据分组。

+ textarea标签

  + 作用：定义一个多行的输入框

  + 格式：

    ```html
    <textarea>
    </textarea>
    ```

  + 注意点：

    + 默认情况下输入框可以无限换行
    + 默认情况下输入框有自己的宽度和高度
    + 可以通过cols和rows来制定输入框的宽度和高度，但是虽然指定了列数和行数，但是还是可以无限往下输入。
    + 默认情况下输入框是可以手动拉伸的。



单选框和多选款当中所有同类选项name属性必须一致。

在表单标签中除了按钮标签，都可以通过value属性指定提交到服务器当中的数据信息。bia