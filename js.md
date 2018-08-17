### 第一章
```
1.JavaScript是一种专为网页交互而设计的脚本语言
①ECMAscript:由ECMA-262定义,提供核心语言功能
②文档对象模型DOM:提供访问和操作网页内容的方法和接口
③浏览器对象模型BOM:提供与浏览器交互的方法和模型
```
### 第二章
```
1.javascript文件放在</body>之前，防止文件脚本过大而造成浏览器呈现页面时的延迟
<body>
    <script type="text/javascript">
    </script>
</body>

2.改变处理脚本的行为
①async(异步脚本)：立即下载脚本
/*只用于外部脚本文件*/
/*不按照顺序执行*/
<head>
    <script type="text/javascript" async src=".js"> </script>
</head>

②defer(延迟脚本)：表示脚本延迟文档完全被解析和显示之后再执行
/*只用于外部脚本文件*/
/*HTML5忽略defer属性*/
<head>
    <script type="text/javascript" defer="defer" src=".js"><script>
</head>
/*延迟脚本不一定按顺序执行，最好只包含一个延迟脚本*/

3.noscript
    <noscript>
        在不支持脚本的浏览器中显示替代内容
    </noscript>

```
### 第三章
```
1.严格模式(ECMAScript5引入)
    function doSomething(){
        "use strict";
    }
    
2.数据类型
    undefined,null,number,string,boolean

  typeof操作符
    undefined：未定义
    boolean：布尔值
    string：字符串
    number：数值
    object：对象或null
    function：函数

    ①alert(null == undefined);   //true
    undefined 无需显式设置
    null 意在保存对象的变量还没有真正保存对象作为空对象指针
    ②boolean(区分大小写)：true或false
    
    ----------------------------------
    数据类型   true           false
    ----------------------------------
    Boolean    true           false
    String     非空字符串     ""空字符串
    Number     非零数值       0或NaN
    Object     对象           null
    Undefined                 undefined
    
    //NaN：not a number
3.浮点数值存在舍入误差问题
  浮点数值最高精度为17位小数
    eg:0.1+0.2 == 0.30000000000000004
  
4.当数值超出js数值范围时，为Infinity

5.数值转换
boolean: true/false  1/0
null: 0
undefined: NaN
字符串:
    "123"  -->123
    "1.1"  -->1.1
    "0xf"  -->十六进制
    空     -->0
    "word" -->NaN

parseInt("10",2);  //2 (二进制解析)
parseInt("10",8);  //8 (八进制解析)

转换成字符串：
    .toString()
    .toString(2)  //输出二进制
    
6.object
    var o = new object();

7.一元操作符
eg:
    var num1 = 2;
    var num2 = 20;
    
    var num3 = --num1 + num2; -->21
    var num4 = num1-- +num2;  -->22
    var num5 = num1 + num2;   -->21
eg:
    var a = false;
    a++;           --->1
    
    var b = {
        valueOf: function(){
            return -1;
        }
    };
    b--;            --->-2
    
eg:
    var num = 25;
    num = +num;     --->25
    //一元加操作符(+)在数值前面，无影响
    
    var num = 25;
    num = -num;     --->-25
    //一元减操作符(-)在数值面前，为负
```
