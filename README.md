# class前端开发流程

1、PS网页设计

2、前端设计（静态页面）

3、后端设计（Java设计动态页面）

# 网页组成部分

1、内容

显示文本

2、表现

布局结构

3、行为

交互响应，一般JavaScript实现

# HTML技术

## HTML书写规范

```html
<!DOCTYPE html><!-- 声明 -->
<html lang="zh_CN"><!-- html标签，表示HTML的开始，zh_CN表示中文，en表示英文 -->
<head><!-- 头部信息，三部分内容：title标签，css样式，js脚本 -->
    <meta charset="UTF-8"><!-- 表示编码格式 -->
    <title>标题</title><!-- 标题 -->
</head>
<body><!-- 表示页面显示主体内容 -->
    hello
</body>
</html>
```

## HTML标签注意

标签大小写不敏感

标签自身属性：

​	基本属性：bgcolor：背景颜色

```html
<body bgcolor="blue">
```

​	事件属性：onclink：点击后响应事件

```html
<button onclick="alert('警告')"></button>
```

标签

​	单标签<xx/>

​	双标签<xx></xx>

## 常用标签

##### font：字体标签，修改字体、颜色、大小

```html
<font color="aqua" face="楷体" size="7">hello</font>
```

##### 特殊字符：显示在文本中

```html
<------------&lt;	
>------------&gt;
space(空格键)-------&nbsp
&lt;br&gt;<!-- 显示<br> -->
```

##### 标题标签

​	h1、h2、h3、h4、h5、h6

​	align属性：对齐属性

```html
<h1 align="left">标题1</h1>
<h2 align="center">标题2</h2>
```

##### 超链接***

```html
<a href="https://www.baidu.com">百度（默认当前窗口）</a>
<a href="https://www.baidu.com" target="_self">百度（当前窗口）</a>
<a href="https://www.baidu.com" target="_blank">百度（新窗口）</a>
```

##### 列表标签

1、无序列表；2、有序列表；3、定义列表

```html
<ul type="none"><!-- 无序列表,type表示显示符号的类别 -->
    <li> 牛一 </li>
    <li> 牛二 </li>
    <li> 牛三 </li>
    <li> 牛四 </li>
</ul>
<hr>
<ol><!-- 有序列表 -->
    <li> 牛一 </li>
    <li> 牛二 </li>
    <li> 牛三 </li>
    <li> 牛四 </li>
</ol>
```

##### img标签：显示图片

​	src:图片路径

​	width、height：宽高

​	border：边界线条宽度

​	alt：路径不存在时显示的信息

```html
<img src="./th.jpg" width="224" height="330" border="1" alt="找不到" />
```

##### 表格标签

​	td：单元格标签

​	tr：行标签

​	th：表头标签

​	b：加粗标签

​	cellspacing：单元格间距

```html
<table width="300" height="300" border="0" cellspacing="0">
    <tr><!--行表格-->
<!--        <td align="center"><b>1.1</b></td>  &lt;!&ndash;加粗居中&ndash;&gt;-->
        <th>1.1</th>  <!--与上述代码效果一致-->
        <th>1.2</th>
        <th>1.3</th>
    </tr>
    <tr>
        <th>2.1</th>
        <th>2.2</th>
        <th>2.3</th>
    </tr>
    <tr>
        <th>3.1</th>
        <th>3.2</th>
        <th>3.3</th>
    </tr>

</table>
```

##### 跨行跨列表格

​	colspan	rowspan

```html
<table width="300" height="300" border="1" cellspacing="0">
    <tr>
        <th colspan="2">1.1</th>
        <th>1.3</th>
        <th>1.4</th>
        <th>1.5</th>
    </tr>
    <tr>
        <th rowspan="2">2.1</th>
        <th>2.2</th>
        <th>2.3</th>
        <th>2.4</th>
        <th>2.5</th>
    </tr>
    <tr>
<!--        <th>3.1</th>-->
        <th>3.2</th>
        <th>3.3</th>
        <th>3.4</th>
        <th>3.5</th>
    </tr>
    <tr>
        <th colspan="2" rowspan="2">4.1</th>
<!--        <th>4.2</th>-->
        <th>4.3</th>
        <th>4.4</th>
        <th>4.5</th>
    </tr>
    <tr>
<!--        <th>5.1</th>-->
<!--        <th>5.2</th>-->
        <th>5.3</th>
        <th>5.4</th>
        <th>5.5</th>
    </tr>
</table>
```

##### iframe框架标签（内嵌窗口）

在html页面内加载一个新页面

```html
<iframe src="th1.jpg" name="abc"> 我是第二个页面</iframe>
<!--    点击下方超链接使第二个页面跳转-->
<ul>
    <li><a href="th2.jpg" target="abc">图片</a> </li>
</ul>
```

##### 表单标签***

表单就是收集用户信息的所有元素集合

```html
<!--
	input type="text"------------单行文本
	input type="password"---------密码
	input type="radio"-----------单选框
	input type="checkbox"--------复选框
	input type="reset"-----------重置按钮
	input type="submit"----------发送按钮
	input type=“button”----------按钮
	input type=“file”------------文件上传域
	input type=“hidden”----------隐藏域，用户看不见，仍可发送
	
	<textarea>----------------多行文本框

	<select>下拉列表	<option>可选项
-->

<!--创建个人信息注册的表单界面， 包含：用户名，密码，确认密码，性别（单选），
兴趣爱好（多选），国籍（下拉列表），隐藏域，自我评价（多行文本域），重置，提交-->
<form>
    用户名称：<input type="text" value="默认值"/><br><!--单行文本-->
    用户密码：<input type="password" maxlength="4"/><br>
    确认密码：<input type="password" maxlength="4"/><br>
    性别： <input type="radio" name="sex" checked="checked"/>男<!--checked="checked"默认选中-->
    <input type="radio" name="sex"/>女<br>
    兴趣爱好： <input type="checkbox" checked="checked"/>读书
    <input type="checkbox"/>Java
    <input type="checkbox"/>Python<br>
    国籍：<select>
    <option>--请选择国籍--</option>
    <option>美国</option>
    <option selected="selected">中国</option> <!--selected默认选中-->
    <option>泰国</option>
        </select><br>
    自我评价：<textarea rows="5" cols="10" >我是多行文本框的默认值</textarea><br>
    <input type="reset" value="重置1"/>
    <input type="submit" value="提交1"/>
</form>
```

##### 表单优化

放入表table中

action:设置提交的服务器（URL+？+提交信息）

method：设置提交方式（默认GET）

​	GET：不安全，有字符长度限制

​	POST：安全，无字符长度限制

表单提交后没有发送的三种情况：

​	1、表单项无name参数

​	2、单选、复选、下拉列表需要加value参数

​	3、表单项不在form标签中

```html
<form action="http://localhost:8080" method="get">
    <h1 align="center">用户注册</h1>
    <input type="hidden" name="隐藏域" value="register"/>
    <table align="center">
        <tr>
            <td>
                用户名称：
            </td>
            <td>
                <input type="text" value="默认值"/><!--单行文本-->
            </td>
        </tr>
        <tr>
            <td>用户密码：</td>
            <td><input type="password" maxlength="4" /></td>
        </tr>
        <tr>
            <td>确认密码：</td>
            <td><input type="password" maxlength="4"/></td>
        </tr>
        <tr>
            <td>性别：</td>
            <td>
                <input type="radio" name="sex" checked="checked"/>男<!--checked="checked"默认选中-->
                <input type="radio" name="sex"/>女
            </td>
        </tr>
        <tr>
            <td>兴趣爱好：</td>
            <td>
                <input type="checkbox" checked="checked"/>读书
                <input type="checkbox"/>Java
                <input type="checkbox"/>Python
            </td>
        </tr>
        <tr>
            <td>国籍：</td>
            <td>
                <select>
                    <option>--请选择国籍--</option>
                    <option>美国</option>
                    <option selected="selected">中国</option> <!--selected默认选中-->
                    <option>泰国</option>
                </select>
            </td>
        </tr>
        <tr>
            <td>自我评价：</td>
            <td>
                <textarea rows="5" cols="10">我是多行文本框的默认值</textarea>
            </td>
        </tr>
        <tr>
            <td><input type="reset" value="重置1"/></td>
            <td><input type="submit" value="提交1"/></td>
        </tr>
    </table>
</form>
```

##### 其他标签

div标签：独占一行

span标签：长度是封装数据的长度

p标签：段落后自动加一空行

```html
<div>div标签</div>
<span>span标签1</span>
<span>span标签2</span>
<p>p标签1</p>
<p>p标签2</p>
```

# CSS技术

将网页样式与内容分离

##### CSS+HTML使用

法1：

```html
<div style="border: blue 1px solid;">div标签1</div>
```

法2：

可以实现**一个页面**的样式复用

```html
<head><!-- 头部信息，三部分内容：title标签，css样式，js脚本 -->
    <style type="text/css">
        /*style标签专门用来定义CSS样式*/
        /*设置所有div标签样式*/
        div{
            border: aqua 1px solid;
        }
    </style>
</head>
```

法3：

实现多个页面样式的复用

```css
div{
    border: black 1px solid;
}
```

设置css文件1.css

```html
 <head>  
	<link rel="stylesheet" type="text/css" href="1.css"/>
</head>
```

html头标签处引入

##### 标签名选择器

上述法2

##### id选择器

设置固定样式供不同id的标签选择，但是每个标签id不同

```html
<head><!-- 头部信息，三部分内容：title标签，css样式，js脚本 -->
    <style type="text/css">
        /*style标签专门用来定义CSS样式*/
        #id0001{
            border: aqua 1px solid;
        }
        #id0002{
            border: black 2px solid;
        }
    </style>
</head>
<body>
    <div id="id0001">div标签1</div>
    <div id="id0002">div标签2</div>
</body>
```

##### class选择器

将标签分类，按照类别设计样式

```html
<head>
    <style type="text/css">
        .class1{
            border: blue 2px solid;
        }
        .class2{
            border: brown 3px dashed;
        }
    </style>
</head>
<body><!-- 表示页面显示主体内容 -->
    <div class="class1">div标签1</div>
    <div class="class2">div标签2</div>
    <div class="class1">div标签3</div>
</body>
```

##### 组合选择器

上述三种选择器组合使用

##### CSS常用样式

color 字体颜色

border 边框

height 块高

width 块宽

background-color 背景颜色

font-size 字体大小

text-align

margin-left，margin-right

text-decoration：auto	超链接去除下划线

##### 浮动

浮动设计的初衷为了解决文字环绕图片问题，浮动后一定不会将文字挡住，这是设计初衷。

##### 定位

position

​	static 默认

​	absolute	绝对位置

​	fixed	相对于浏览器窗口

​	relative	相对于元素原本位置

##### 盒子模型

像套盒子一样管理

# JavaScript技术

弱类型语言

特点：交互性

​			安全性，不允许直接访问本地硬盘

​			跨平台性

##### HTML+JavaScript使用

法1

```html
<script type="text/javascript">
    alert("hello JavaScript")
</script>
```

将代码放入head或body均可

法2

```javascript
alert("hello JavaScript")
```

新建文件1.js

```html
<script type="text/javascript" src="1.js"></script>
```

在html引入文件

注意：script标签法1、法2都适用，但不能同时在一个script标签使用

##### JS变量

变量类型：数值型、字符串类型、对象类型object布尔类型、函数类型

特殊值：undefined（变量未赋初始值），null（空值），NAN（非数字）

定义变量格式：var 变量名=值；

##### 比较运算

==和===

==：字面值的比较

===：字面值&类型的比较

```javascript
var i = "12";
var j = 12.0;
alert(i===j)//false
var i = 12;
var j = 12.0;
alert(i===j)//true
```

##### 逻辑运算

注：所有变量都可以当做布尔类型使用

0、null、undefined、“”为false

&&：表达式全为true返回最后一个表达式值，为false时返回第一个为false的值

||：表达式全为false返回最后一个表达式值，为true时返回第一个为true的值

##### 数组***

var 变量名 = []

```javascript
var arr = []
// alert(arr.length) //0
arr[0] = 1
// alert(arr.length)//1
arr[2] = 2
alert(arr.length) //3
```

数组可以自动扩展长度，未定义的中间值为“undefined”

数组是有在赋值时才可能扩容

##### 函数***

函数定义法1：

```javascript
function f1() {
    alert("无参函数f1()被调用")
}

function f2(a, b) {
    alert("有参函数f2(a, b)被调用a:" + a + ",b:" + b)
}

function f3(num1, num2) {
    // 带有返回值的函数
    return num1 + num2
}

// f1()
// f2(1, 2)
// alert(f3(1, 2))
```

函数定义法2

```javascript
var f = function () {

}
f()
```

函数隐形参数

```javascript
function f() {
    // alert("隐含参")
    for (var i = 0; i<arguments.length;i++)
        alert(arguments[i])
    // alert(arguments.length)
}
f("a", "b")
```



注意：

```javascript
function f() {
    alert("无参")
}
function f(a, b) {
    alert("有参")
}

// f()
```

js不允许函数重载，函数会被覆盖

##### 自定义对象

1、object形式自定义对象

对象定义：

var 变量名 = new Object() 

变量名.属性名 = 值

变量名.函数名 = function(){}

对象访问：

变量名.属性名/函数名(参数)

2、{}形式自定义对象

var 对象名 = {

​	属性名：值，

​	函数名： function(){}

}

```javascript
var obj = {
    name:"hxx",
    age:10,
    f:function (a,b) {
        alert(a+b)
    }
}
alert(obj.name)
```

##### 事件介绍

常用事件：

onload加载完成事件：页面加载完后自动执行的操作，常用于页面js代码初始化操作

onclick单击事件：常用于按钮的点击响应操作

onblur失去焦点事件：常用于输入框失去焦点后验证其输入内容是否合法

onchange内容发生改变事件：常用于下拉列表、输入框内容发生改变后操作

onsubmit表单提交事件：常用于表单提交前，验证所有表单项是否合法

##### 事件注册或绑定

事件注册：事件响应时执行哪些代码

静态注册事件:通过 html标签的事件属性直接赋于事件响应后的代码，这种方式我们叫静态注册。
动态注册事件:是指先通过js代码得到标签的 dom 对象,然后再通过 dom 对象,事件名 =function(){} 这种形式赋于事件响应后的代码，叫动态注册。

动态基本步骤：1、获取标签对象；2、标签对象.事件名 = function(){}

##### 事件举例

onload事件

```html
<body onload="alert('静态注册onload浏览器自动执行')"></body>
```

```html
<script type="text/javascript">
    window.onload = function () {
        alert("动态注册实现onload事件")
    }
</script>
```

onclick事件

```html
<!DOCTYPE html><!-- 声明 -->
<html lang="zh_CN"><!-- html标签，表示HTML的开始，zh_CN表示中文，en表示英文 -->
<head><!-- 头部信息，三部分内容：title标签，css样式，js脚本 -->
    <meta charset="UTF-8"><!-- 表示编码格式 -->
<title>表单</title><!-- 标题 -->
<!--<script type="text/javascript" src="1.js"></script>-->
<script type="text/javascript">
    function f() {
        alert("静态注册onclick事件")
    }

    window.onload = function () {
        //动态注册
        //1、根据ID获取标签对象
        var butObj = document.getElementById("butObj")
        //2、确定标签对象onclick的函数操作
        butObj.onclick = function () {
            alert("动态注册onclick事件")
        }
    }
    
</script>
</head>
<body><!-- 表示页面显示主体内容 -->
    <button onclick="f()">按钮1</button>
    <button id="butObj">按钮2</button>
</body>
</html>
```

onblur事件

```html
<!DOCTYPE html><!-- 声明 -->
<html lang="zh_CN"><!-- html标签，表示HTML的开始，zh_CN表示中文，en表示英文 -->
<head><!-- 头部信息，三部分内容：title标签，css样式，js脚本 -->
    <meta charset="UTF-8"><!-- 表示编码格式 -->
<title>表单</title><!-- 标题 -->
<!--<script type="text/javascript" src="1.js"></script>-->
<script type="text/javascript">
    function f() {
        console.log("静态注册失去焦点")
    }

    window.onload = function () {
        var buttonObj = document.getElementById("buttonObj");
        buttonObj.onblur = function () {
            console.log("动态注册失去焦点")
        }
    }

</script>
</head>
<body><!-- 表示页面显示主体内容 -->
    <button onblur="f()">按钮1</button><br/>
    <button id="buttonObj">按钮2</button>
</body>
</html>
```

onchange事件

```html
<!DOCTYPE html><!-- 声明 -->
<html lang="zh_CN"><!-- html标签，表示HTML的开始，zh_CN表示中文，en表示英文 -->
<head><!-- 头部信息，三部分内容：title标签，css样式，js脚本 -->
    <meta charset="UTF-8"><!-- 表示编码格式 -->
    <title>表单</title><!-- 标题 -->
    <!--<script type="text/javascript" src="1.js"></script>-->
    <script type="text/javascript">
        function f() {
            alert("静态注册实现onchange事件")
        }

        window.onload = function () {
            var buttonObj = document.getElementById("selectObj");
            buttonObj.onblur = function () {
                alert("动态注册实现onchange事件")
            }
        }

    </script>
</head>
<body><!-- 表示页面显示主体内容 -->
<select onchange="f()">
    <option>--技能--</option>
    <br/>
    <option>C++</option>
    <br/>
    <option>Java</option>
    <br/>
    <option>Python</option>
</select><br/>
<select id="selectObj">
    <option>--爱好--</option>
    <br/>
    <option>唱歌</option>
    <br/>
    <option>跳舞</option>
    <br/>
    <option>Rap</option>
    <br/>
    <option>篮球</option>
</select>
</body>
</html>
```

onsubmit事件

```html
<!DOCTYPE html><!-- 声明 -->
<html lang="zh_CN"><!-- html标签，表示HTML的开始，zh_CN表示中文，en表示英文 -->
<head><!-- 头部信息，三部分内容：title标签，css样式，js脚本 -->
    <meta charset="UTF-8"><!-- 表示编码格式 -->
    <title>表单</title><!-- 标题 -->
    <!--<script type="text/javascript" src="1.js"></script>-->
    <script type="text/javascript">
        function f() {
            alert("静态注册实现onsubmit事件-----静态注册不合法")
            // return false // 不提交
            return true //提交
        }

        window.onload = function () {
            var buttonObj = document.getElementById("submitObj");
            buttonObj.onsubmit = function () {
                alert("动态注册实现onsubmit事件----不合法")
                // return false
                return true
            }
        }

    </script>
</head>
<body><!-- 表示页面显示主体内容 -->
<form action="http://localhost:8080" method="get" onsubmit="return f()">
    <input type="submit" value="静态注册" ><br/>
</form>
<form action="http://localhost:8080" method="get" id="submitObj">
    <input type="submit" value="动态注册" >
</form>
</body>
</html>
```

##### DOM-文档对象模型***

1、Document对象

Document 对象的理解
第一点:Document 它管理了所有的 HTML 文档内容。

第二点:document 它是一种树结构的文档。有层级关系。

第三点:它让我们把所有的标签 都 对象化

第四点:我们可以通过 document 访问所有的标签对象。

2、Document对象方法

document.getElementByID()：根据ID返回首个

document.getElementByName()：根据name可以返回多个

documen.getElementByTagName()：根据标签名返回多个

notes：

优先使用级别：ID->Name->TagName

方法只有页面初始化后才能查到元素，即Document方法不能写在函数外

##### 正则表达式

和java、python类似

##### jQuery

1、jQuery介绍

js+Query（查询），辅助js的类库

2、JQuery使用

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>jQuery使用</title>
    <script type="text/javascript" src="./jquery-3.7.1.js"></script>
    <script type="text/javascript">
        // window.onload = function () {
        //     var butObj = document.getElementById("butId");
        //     butObj.onclick = function () {
        //         alert("HelloWorld")
        //     }
        // }
        $(function () {//表示页面加载完成之后，相当于window.onload = function（）{}
            var $butObj = $("#butId");//根据ID获取对象
            $butObj.click(function () {//对对象绑定事件
                alert("单击事件")
            });
        });
    </script>
</head>
<body>
    <button id="butId">SayHello</button>
</body>
</html>
```

$功能：

$+函数：页面加载完后自动调用函数

$+HTML字符串：根据字符串创建元素节点对象

```html
$(function () {
    $("<button id=\"butId\">SayHello</button>").appendTo("body");
});
```

$+选择器字符串：根据选择器查询标签对象。例：$(#id属性值)；$(标签名);$(".class属性值")

$+DOM对象：DOM对象转换为jQuery对象

jQuery对象实质：DOM对象的数组+jQuery提供的一系列功能函数

##### jQuery选择器***

###### 基本选择器：

标签选择器、ID选择器、属性class选择器和组合选择器

###### 层级选择器

后代选择器：

后代选择器：祖先标签 后代标签；选择所有的后代标签

子元素选择器：父标签 > 子标签；选择子类标签

相邻元素选择器：prev+next ；选择紧邻prev元素后的next元素

之后的兄弟元素选择器：prev~sibings；匹配prev之后的所有sibings元素

###### 过滤选择器

1、基本过滤选择器

:first	:last	:not(select)	:even:查找索引值为偶数的标签

:odd:查找索引值为奇数的标签

2、内容过滤器

:contains(text)：查找包含给定文本的元素

:empty：匹配所有不包含子元素或文本为空的元素

:parent：匹配非空元素

3、属性过滤器

[attribute]：匹配包含给定属性的元素

[attribute=value]

[attribute!=value]

[attribute^=value]：属性以value开头元素

[attribute$=value]：以value结尾

[attribute*=value]：包含value的元素

符合属性选择器[][][属性条件1] [属性条件2] ...

4、表单过滤器

[:input]

[:text]

[:password]

5、表单对象属性

:enabled

:disabled

:checked

:selected

##### jQuery元素筛选

eq()、first()、last()、filter()、is()、has()、not()、children()、find()、next()、nextAll()、nextUntil()、parent()、prev()、prevAll()、prevUntil()、siblings()、add()

##### jQuery属性操作

html()：可以设置、获取起始标签、结束标签之间的内容。和dom属性innerHTML一样

text()：可以设置、获取起始标签、结束标签之间的文本。和dom属性innerText一样

val()：可以设置、获取表单项的属性值，和dom的value一样

attr()：可以设置、获取属性值，未定义的参数会返回undefined,不推荐操作checked、readOnly、selected、disabled...

prop()：可以设置、获取属性值，prop可以查看复选框是否选中，返回true和false，适用于attr()不适合的

##### jQuery操作例子：

```html
<!DOCTYPE html>
<html lang="zh_CN">
<head>
    <meta charset="UTF-8">
    <title>jQuery使用</title>
    <script type="text/javascript" src="./jquery-3.7.1.js"></script>
    <script type="text/javascript">
        $(function () {
            // 全选按钮
            $("#checkedAllBtn").click(function () {
                $(":checkbox").prop("checked", true)
            });
            // 全不选按钮
            $("#checkedNoBtn").click(function () {
                $(":checkbox").prop("checked", false)
            });
            // 反选按钮-需要判断反选后是否全选
            $("#checkedRevBtn").click(function () {
                // alert( $(":checkbox[name='items']:checked").length )
                if ( $(":checkbox[name='items']:checked").length  == 0 ) {
                    $("#checkAllBox").prop("checked", true);
                }
                else {
                    $("#checkAllBox").prop("checked", false);
                }
                $(":checkbox[name='items']").each(function () {
                    this.checked = !this.checked
                })
            });
            // 提交按钮
            $("#sendBtn").click(function () {
                $(":checkbox[name='items']:checked").each(function () {
                    alert(this.value)
                });
            });
            // 全选/全不选复选框
            $("#checkedAllBox").click(function () {
                // $(":checkbox[name='items']").prop("checked", $("#checkAllBox").prop("checked")==true)
                $(":checkbox[name='items']").prop("checked", this.checked==true)
            });
            // 每个复选框绑定事件，判断全选/全不选复选框是否选择
            $(":checkbox[name='items']").click(function () {
                // 检查复选框操作后是否满选
                var allLength = $(":checkbox[name='items']").length;
                var checkedLength = $(":checkbox[name='items']:checked").length;
                $("#checkedAllBox").prop("checked", allLength == checkedLength);
            });
        });
    </script>
</head>
<body>
    <form mathod="post" action="">
        你爱好的运动是？<input type="checkbox" id="checkedAllBox"/>全选/全不选
        <br/>
        <input type="checkbox" name="items" value="足球"/>足球
        <input type="checkbox" name="items" value="篮球"/>篮球
        <input type="checkbox" name="items" value="羽毛球"/>羽毛球
        <input type="checkbox" name="items" value="乒乓球"/>乒乓球
        <br/>
        <input type="button" id="checkedAllBtn" value="全选"/>
        <input type="button" id="checkedNoBtn" value="全不选"/>
        <input type="button" id="checkedRevBtn" value="反选"/>
        <input type="button" id="sendBtn" value="提交"/>


    </form>
</body>
</html>
```

##### DOM操作

内部插入：

appendTo()

prependTo()

外部操作：

insertAfter()

insertBefore()

替换

a.replaceWith(b):用b替换掉a

a.replaceAll(b):用a替换所有b

删除

a.remove():删除a整个内容

a.empty():清空标签a内的内容

# JSON串

可以实现前后端传送数据

+ 通过JSON.parse()方法可以将一个JSON串转换成对象

+ 通过JSON.stringify()方法可以将一个对象转换成一个JSON格式的字符串

# 附

###### 注释符

| HTML        | CSS          | JavaScript |
| ----------- | ------------ | ---------- |
| <!--注释--> | /\* 注释 \*/ | //注释     |

