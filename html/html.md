# HTML

## 基础知识

* 常见浏览器: IE、火狐、google safari Opera

* 渲染引擎 ：浏览器渲染时 有渲染引擎=浏览器内核

  | 浏览器       | 内核               |
  | ------------ | ------------------ |
  | IE           | Trident            |
  | Firefox      | Gecko              |
  | Safari       | Webkit             |
  | Chrome/Opera | Blink(webKit 分支) |

* web标准

  希望用什么浏览器打开都是一样的，内核不一样

![截屏2022-04-25 下午12.48.42](/Users/zq2lii/Library/Application Support/typora-user-images/截屏2022-04-25 下午12.48.42.png)

## 网页的固定结构 - html的骨架结构 ##

```html
<!DOCTYPE html>
<html lang="en">
	<head>
    <meta charset="UTF-8">
		<title> 浏览器标签上的名字<\title>
	<\head>
	<body>
		网页的主体内容
	<\body>
<\html>
```

* 注释

​		`<!--  -->`

​		VScode 快捷键 ctrl + /

* html标签的构成

  `<strong> 包裹的内容 <\strong>`

  开始标签 + 包裹内容 + 结束标签

  * strong为标签名
  * 常见标签由两部分组成 双标签 中间有包裹内容
  * 少数标签由一部分组成 但标签 `<br> <hr>`

  - 怎么记住？ 不需要确定开始结束 没有包裹内容 则为单标签

* 标签的关系

  * 嵌套关系

    ```html
    <head>
    	<title> <\title>
    <\head>
    ```

    

  * 并列关系

    ```
    <head><\head>
    <body><\body>标签学习
    ```


## 标签学习

### 排版标签 ### 

#### 	1. 标题标签

 h系列标签 最多6个 和markdown一样分六级

```html
<h1> <\h1>
<h2> <\h2>
<h3> <\h3>
<h4> <\h4>
<h5> <\h5>
<h6> <\h6>
```

快捷键 cmd+d 会一个一个选中相同的内容

#### 	2. 段落标签

```
<p> <\p>
```

调整两个段落之间的缝隙用css

两个段落中间有缝 独占一行

#### 	3. 换行标签

```
<br>
```

表示换行 没有开头和结尾

#### 	4. 水平线标签

```html
<hr>
```

### 文本格式化标签

#### 1. 加粗 下划线 倾斜 删除线

| 说明    | 标签   |
| ------- | ------ |
| b加粗   | strong |
| u下划线 | Ins    |
| i倾斜   | em     |
| s删除线 | Del    |

不会自动换行 都会放在一行里

### 媒体标签

#### 1. 图片标签

```
<img src="" alt="">

example 2:
<img src="planets.gif" width="145" height="126" alt="Planets" usemap="#planetmap">

<map name="planetmap">
  <area shape="rect" coords="0,0,82,126" href="sun.htm" alt="Sun">
  <area shape="circle" coords="90,58,3" href="mercur.htm" alt="Mercury">
  <area shape="circle" coords="124,58,8" href="venus.htm" alt="Venus">
</map>

```

1. **标签属性** ：src属性名 =“属性值” ：属性 alt是替换文本 当图片加载不出来 用这个文字表示 alt和src之间只有一个能显示

2. 一个标签可以存在多个属性，多个属性之间和标签名之间都用空格隔开

3. 属性之间没有顺序

4. 还可以添加的其他属性 

   1. title 提示文本 鼠标悬停显示文本 哪个标签都可以用
   2. width和height 如果只设置一个 自动等比例缩放 同时设置时可能会变形

5. 图片/文件的路径 分为相对路径和绝对路径(从盘符开始或者是网址)

   1. ​	相对路径更加常用 从当前文件开始出发寻找文件的路径
   2. 分为同级（在一个文件夹里 直接文件名 or./） 上级（回到上级../）和下级 (./文件夹/图片名)

6. <map>标签 可以在图片的不同区域增加新的超链接 通过img标签中的usemap属性 使用map中的name属性 map标签是个双标签 内部嵌套多个area标签用来规定不同的区域

#### 2. 音频标签

```
<audio src="" alt=""></audio>
```

常见属性：

​	src 音频的路径

​	controls 显示播放的空间 只写controls就行

​	autoplay 自动播放 但是部分浏览器不支持

​	loop 循环播放

目前支持的三种格式mp3，wav和ogg

#### 3. 视频标签

```
<video src=""></video>
```

常见属性

​	同音频

​	muted 静音播放 此情况下可以自动播放

### 链接标签

点击之后从一个页面跳转到另一个页面

称呼：a标签 超链接 锚链接

```
<a href="">超链接</a>
<a id="tips">有用的提示部分</a>
<a href="#tips">有用的提示部分</a>
```

特点：

​	双标签 内部可以包裹内容

​	如果需要a标签点击之后去指定页面 需要设置href属性

​	#表示空地址

常用属性

​	href表示跳转的地址 可以本地的html文件 or某个网页

​	target 表示跳转方式 2种值 _self（覆盖原网页默认值） or _blank保留原网页

**一个网站首页html文件命名为 index文件**



## 列表标签

#### 无序列表 

没有123 只是从上到下列出来

```
<ul>
	<li>apple</li>
	<li>banana</li>
	<li>pear</li>
</ul>
```

1. 列表每一项前面都是圆圈开头
2. ul标签中只能包含li标签
3. li标签内可以包含任意内容

#### 有序列表 

比如微博热搜排名

```
<ol>	
	<li>apple</li>
	<li>banana</li>
	<li>pear</li>
</ol>
```

#### 自定义列表

- dl 自定义列表的整体 用于包裹dt dd标签

- dt 自定义列表的主题

- dd 针对主题的每一项内容

  ```
  <dl>
          <dt>帮助中心</dt>
              <dd>账户管理</dd>
              <dd>购物指南</dd>
  </dl>
  ```

* ul是unordered lists的缩写 (无序列表)

  li是list item的缩写 （列表项目）

  ol是ordered lists的缩写（有序列表）

  dl是definition lists的英文缩写 (自定义列表)

  dt是definition term的缩写 (自定义列表组)

  dd是definition description的缩写（自定义列表描述）

  nl是navigation lists的英文缩写 （导航列表）

  tr是table row的缩写 （表格中的一行）

  th是table header cell的缩写 （表格中的表头）

  td是table data cell的缩写 （表格中的一个单元格）

## 表格标签

- 标签

  - table 表格整体 用于包裹多个tr

  - tr 表格每行 

  - td 表示每行的每个项 th表示标题行中的每一项

  - <colgroup> 双标签 用于对column进行划分 定义不同的背景颜色等

  - <col> 是<colgroup>标签的内部定义列分组的标签 其中**span**属性表示每个列分组跨的列数 默认是1

    ```
    <table border="1">
      <colgroup>
        <col span="2" style="background-color:red">
        <col style="background-color:yellow">
      </colgroup>
      <tr>
        <th>ISBN</th>
        <th>Title</th>
        <th>Price</th>
      </tr>
      <tr>
        <td>3476896</td>
        <td>My first HTML</td>
        <td>$53</td>
      </tr>
    </table>
    
    ```

  - <thead> 在tr/th外面再嵌套一层

  - <tbody>

  - <tfoot>

- 常用标签属性

  - border 数字 边框宽度 写上这个属性才会有边框
  - width 数字 表格宽度
  - height 数字 表格高度
  - 实际开发过程中 用css来进行设置

- 常用的其他 **标签**

  - caption 表格大标题 写在table标签内部
  - th 标题行加粗效果 在tr内包裹的 代替普通的td 大部分浏览器会把表头渲染成居中加粗

- 表格的**结构标签**

  - 用来对不同行 tr进行包裹
  - thead
  - tbody
  - tFoot

- 合并单元格

  - 将水平或垂直的多个单元格合并成一个单元格
  - 根据左上原则 删除要被删除的单元格
  - 在要**保留的单元格**处增加属性 rowspan or colspan 

## 表单标签

- html表单用于收集不同类型的用户输入

### input系列标签

- input系列标签 button按钮标签 select下拉菜单标签 textarea文本域标签 label标签

- 表单是一个包含表单元素的区域。

  表单元素是允许用户在表单中输入内容,比如：文本域(textarea)、下拉列表、单选框(radio-buttons)、复选框(checkboxes)等等。

  表单使用表单标签 <form> 来设置 input标签 单标签

  ```
  <form>
  First name: <input type="text" name="firstname"><br>
  Last name: <input type="text" name="lastname">
  </form>
  ```

  - 输入元素 `<input type="text" name="firstname">`

  - 密码字段 `<input type="password" name="pwd">`

  - 单选按钮`<input type="radio" name="sex" value="female">Female` radio buttons

  - 复选框checkboxes`<input type="checkbox" name="vehicle" value="Car">I have a car`

  - 提交按钮 submit button `<input type="submit" value="Submit">`

  - 自定义一个按钮 `<input type="button" value="Hello world!">`

  - 下拉

    ```
    <select name="cars">
    <option value="volvo">Volvo</option>
    <option value="saab">Saab</option>
    <option value="fiat" selected>Fiat</option>
    <option value="audi">Audi</option>
    </select>
    ```

  - ```
    <textarea rows="10" cols="30">
    我是一个文本框。
    </textarea>
    ```

  - input标签总结 可以通过type属性值的不同 展示不同的效果 input标签默认不会换行

  - type Reset和submit 想要使用 必须要提供表单域 都要放在form中

  - type button就是一个按钮 跳转或者功能添加 在js中添加

    ![image-20220425215203297](/Users/zq2lii/Library/Application Support/typora-user-images/image-20220425215203297.png)

  - 常用属性 
    - placeholder 占位符 提示用户输入内容的文本针对text和password的type
    - name属性在radio type中用于分组 一组中只能选一个 比如男女的单选 增加一个name属性值为sex
    - **checked**属性在radio/checkbox type中用于默认选中 只加一个单词就行
    - 上传文件 type为file时 增加multiple属性 从而允许上传多个文件
    - 改变按钮的提示名称 比如默认提交 修改value属性即可

### Button按钮标签

- 标签名 button 双标签 中间包裹内容是按钮名称
- type属性名 submit reset button reset这个标签要填在form的里面

### select下拉菜单

- 提供多个选择项的下拉菜单表单控件
- 标签组成
  - 标签 select 下拉菜单整体
  - 标签option 下拉菜单的每一项
- 常见属性
  - **selected** 下拉菜单的默认选中

### textarea文本域标签

- 标签名 textarea
- 属性 cols 和 rows 填数字 调宽度 以后不是通过属性调整 而是通过css调整具体大小

### label标签

- 在单选框的时候 不点圈圈 点字也可以
  - 方法1:
    -  label标签把内容包裹起来
    - 表单标签上添加id属性
    - label标签的for属性中设置对应的id属性值
  - 方法2:
    - 直接用label标签把内容和表单标签一起包裹起来
    - label中的for属性不用使用

## 语义化标签

- 没有语义的布局标签 div 和 span 
  - div 
  - span 都是双标签
- 有语义的布局标签
  - html5中新推出的标签 做手机端网页时使用 在网页版显示时和分开用div包裹了几句话一样 没有区别
  - header
  - nav
  - footer
  - aside
  - section
  - article
  - ![image-20220425223952431](/Users/zq2lii/Library/Application Support/typora-user-images/image-20220425223952431.png)

## 字符实体

能通过字符实体在网页中显示特殊符号

#### html中的空格合并现象

- 网页不认识多个空格 添加多个 但是只显示1个 空格&nbsp

- 常见字符实体 空格&nbsp

## 综合案例

## HTML 区块和布局

- html的元素<>可以分为区块元素（另起一行 结束换行）和内联元素（像加粗等 不换行 比如latex加公式这种）

- `<div>`将不同元素组成区块

- `<span>`将不同元素内联

  ```
  <!DOCTYPE html>
  <html>
  <head> 
  <meta charset="utf-8"> 
  <title>菜鸟教程(runoob.com)</title> 
  </head>
  <body>
   
  <div id="container" style="width:500px">
   
  <div id="header" style="background-color:#FFA500;">
  <h1 style="margin-bottom:0;">主要的网页标题</h1></div>
   
  <div id="menu" style="background-color:#FFD700;height:200px;width:100px;float:left;">
  <b>菜单</b><br>
  HTML<br>
  CSS<br>
  JavaScript</div>
   
  <div id="content" style="background-color:#EEEEEE;height:200px;width:400px;float:left;">
  内容在这里</div>
   
  <div id="footer" style="background-color:#FFA500;clear:both;text-align:center;">
  版权 © runoob.com</div>
   
  </div>
   
  </body>
  </html>
  ```

  ![截屏2022-04-25 下午9.09.40](/Users/zq2lii/Library/Application Support/typora-user-images/截屏2022-04-25 下午9.09.40.png)



## 几个属性的区分

name 用在单选分组 限制只选一个

value 用在修改input按钮的显示值 目前理解 没有中间包裹的内容 所以需要在标签头通过属性来修改

id 跳转用？在超链接的时候 如果某个id已经赋值 后面的调用可以通过#id来调用 相当于加了个全局（存疑）变量