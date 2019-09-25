## Javascript笔记

### **1.基本语法**

> 1. 用<script>嵌入至html内，它可以在html语句体任意位置，但是会影响到它执行顺序一般嵌入在<head>标签体内
>
>    * 内部js : 就是<script>置于html体内
>    * 外部js : 利用<script src=" ">获取外部的js文件
>
> 2. 因为JavaScript是弱类型语言，所以它只需定义变量无需确定数据类型
>
>    * 原始数据类型
>      * number ：数字。 整数/小数/NaN(not a number 一个不是数字的数字类型)
>      * string :字符串。 字符串  "abc" "a" 'abc'
>      * boolean :true和false
>      * null :一个对象为空的占位符
>      * undefined :未定义。如果一个变量没有给初始化值，则会被默认赋值为undefined
>    * 引用数据类型：对象(null返回object是js的bug)
>
>    变量定义： var 变量名=初始化值；
>
>    返回变量的数据类型：typeof(变量)
>
> 3. 流程控制语句
>
>    * switch: 
>
>      * 在java中，switch语句可以接受的数据类型： byte int shor char,枚举(1.5) ,String(1.7)
>
>      * 在js中可以接受任意类型。switch(变量){case 1:  ;case 2: ;}
>
>    * if else、while、do while、for与Java差不多

### **2.javascript对象**

>* 基本对象
>
> 1. Function ：函数对象
>
>    * 创建：
>    
>       ~ ： `var fun = new Function(形参列表，函数体);`//忘记吧
>    
>        ~ ： function 方法名称(参数列表){
>    
>        ​           方法体
>    
>        ​        }
>    
>        ~ ：  var 方法名 = function(形式参数列表){
>                                方法体
>                }
>    
>    * 属性：
>    
>       length:代表形参的个数 即`fun.length`、或是`方法名.length`
>    
>    * 特点：
>    
>        ~ ：方法定义是，形参的类型不用写,返回值类型也不写。
>    
>        ~ ：方法是一个对象，如果定义名称相同的方法，会覆盖
>    
>        ~ ：在JS中，方法的调用只与方法的名称有关，和参数列表无关
>    
>        ~ ：在方法声明中有一个隐藏的内置对象（数组），arguments,封装所有的实际参数，当传入的参数个数大于形式参数个数
>
> 2. Array对象
>
>    * 创建 ：
>    
>        ~ : var arr = new Array(元素列表);
>    
>        ~ : var arr = new Array(默认长度)；
>    
>        ~ : var arr = [元素列表];
>    
>    * 方法  :  
>    
>        ~ ：join(参数):将数组中的元素按照指定的分隔符拼接为字符串
>    
>        ~ ：push()	向数组的末尾添加一个或更多元素，并返回新的长度
>    
>    * 属性 ：
>    
>        ~ ：length 数组长度
>    
>    * 特点 ：
>    
>       ~ ：数组元素类型可变
>    
>       ~ ：数组长度可变
>
> 3. Date对象
>
>    * 创建 ：
>    
>        var date = new Date();
>    
>    * 方法 ：
>
>​                ~ ：toLocaleString() //返回当前date对象对应的时间本地字符串格式
>
>​                ~ ：getTime() //获取毫秒值。返回当前如期对象描述的时间到1970年1月1日零点的毫秒值差
>
> 4. Math对象
>
>    * 创建 : 无需创建
>    * 方法
>
>    ​        ~ :random() :返回 0 ~ 1 之间的随机数。 含0不含1
>
>    ​        ~ : ceil() : 对数进行上舍入
>
>    ​        ~ : floor() : 对数进行下舍入
>
>    ​        ~ :round() : 把数四舍五入为最接近的整数
>
>    ​        ~ :PI 是它的属性
>
>5. RegExp对象 :正则表达式对象
>
>   * 正则表达式 ：
>
>     * 单个字符 : []
>
>       如： [a] [ab] (a或b)[a-zA-Z0-9_]
>
>       特殊符号代表特殊含义的单个字符:
>       						\d:单个数字字符 [0-9]
>       						\w:单个单词字符[a-zA-Z0-9_]
>
>     * 量词符号 ：
>
>       ?：表示出现0次或1次
>       *：表示出现0次或多次
>       +：出现1次或多次
>       {m,n}:表示 m<= 数量 <= n
>
>       * m如果缺省： {,n}:最多n次
>       *  n如果缺省：{m,} 最少m次
>
>     * 开始结束符号 ：
>
>       ^ : 开始
>
>       $ : 结束
>
>   * 正则对象 ：
>
>     * 创建 ：
>
>       ~ ：var reg = new RegExp("正则表达式");
>
>       ~ ：var reg = /正则表达式/;
>
>     * 方法 ：
>
>       ~ ：test(参数):验证指定的字符串是否符合正则定义的规范，返回布尔类型	
>
>   
>
>6. Global对象 :

## **3.DOM**

> 1. DOM：Document Object Model 文档对象模型
>
>    * 功能：
>      * 控制html文档的内容
>      * 获取页面标签(元素)对象：Element //document.getElementById("id值"):通过元素的id获取元素对象
>    * 操作Element对象：
>      * 修改属性值：
>        1. 明确获取的标签对象是谁
>        2. 查看W3C文档，查看该对象的属性有哪些
>      * 修改标签体内容：innerHTML
>        1. 获取元素对象
>        2. 使用innerHTML修改标签体内容
>    * 的
>
> 2. 事件：某些组件被执行了某些操作后，触发某些代码的执行
>
>    * 绑定事件：
>
>      1. 直接在html标签上，指定事件的属性(操作)，属性值就是js代码  //onclick--- 单击事件
>
>         ```javascript
>         <img id=light src="img/off.gif" onclick="alert('我被点了');"> //注意alert的那些符号 缺点html标签与事件耦合度太高了
>             
>         <body>
>         			<img id="light" src="img/off.gif"  onclick="fun();">
>         			<img id="light2" src="img/off.gif">
>         			
>         			<script>
>         			    function fun(){
>         			        alert('我被点了');
>         			        alert('我又被点了');
>         			    }	
>         			</script>
>         </body>
>         ```
>
>      2. 通过js获取元素对象，指定事件属性，设置一个函数
>
>         ```javascript
>         <!DOCTYPE html>
>         <html lang="en">
>         <head>
>             <meta charset="UTF-8">
>             <title>事件绑定</title>
>         </head>
>         <body>
>            <img id="p1" src="img/off.gif">
>         
>         </body>
>         <script>
>             function fun() {
>                 alert("点我干什么");
>             }
>             var p1=document.getElementById("p1");//不能没有双引号
>             p1.onclick=fun;//不能加括号
>         </script>
>         </html>
>         ```
>
>      3. kkkkk
>
> 3. 到底
>
>    

## **4.BOM**

>1. **BOM :**Browser Object Model 浏览器对象模型
>
>   * 将浏览器各个组成部分封装成对象
>
>     * **Window**：窗口对象
>
>     * Navigator ：浏览器对象 
>
>     * Screen : 显示器屏幕对象
>
>     * History：历史记录对象
>
>     * Location ：地址栏对象
>
>       ![](C:\Users\Administrator\github\images\js\js_BOM.png)
>
>2. **window对象**
>
>   * 创建：
>
>   * 方法：
>
>     1. 弹出的方法
>
>        - alert() :显示带有一段消息和一个确认按钮的警告框
>
>        - confirm() : 显示带有一段消息以及确认按钮和取消按钮的对话框,用户点击确定则返回ture,否则false
>
>          ![](C:\Users\Administrator\github\images\js\confirm.png)
>
>        - prompt() : 显示可提示用户输入的对话框,返回值返回用户输入的值，括号内可以写入提示信息
>
>     2. 打开关闭方法
>
>        * close() :关闭浏览器窗口,谁调用我,我关谁
>        * open() :打开一个新的浏览器窗口,返回新的Window对象可以被close()关闭使用,括号内输入打开的网址
>
>     3. 与定时器有关的对象
>
>        * setTimeout(参数1，参数2) :在指定的毫秒数后调用函数或计算表达式
>          1. js代码或者方法对象
>          2. 毫秒值
>          3. 返回值：唯一标识，用于取消定时器
>        * clearTimeout() :取消由 setTimeout() 方法设置的 timeout
>        * setInterval() :按照指定的周期（以毫秒计）来调用函数或计算表达式
>        * clearInterval() :取消由 setInterval() 设置的 timeout
>
>     4. 轮播图：
>
>        ![](C:\Users\Administrator\github\images\js\轮播图.png)
>
>   ​        
>
>   * 属性：
>
>     * 获取其他四个BOM对象
>
>       ~ ：就是说`var v = window.history`==`var v2=history`
>
>     * 获取DOM对象
>
>       ~   : `window.document.getElementById()`==`document.getElementById`// 上面的截图有document对象是包含在window对象里的是window的属性。
>
>   * 特点：直接调用Window对象不需要创建可以直接使用 window使用。 window.方法名();
>
>     window引用可以省略 方法名();如：`window.alert()`==`alert()`
>
>3. **Location对象** 
>
>   * 创建：
>
>     * window.location
>     * location
>
>   * 方法：
>
>     reload() : 重新加载当前文档。刷新
>
>   * 属性：
>
>     href :设置或返回完整的 URL
>
>4. **Element对象** 
>
>   * 创建：通过document来获取和创建
>   * 方法：
>     * setAttribute():设置属性
>     * removeAttribute() :删除属性
>
>5. **Node对象**
>
>   * 特点：可被认为是其他所有dom对象的父对象
>   * 方法：CURD dom树
>     * appendChild() :向节点的子节点列表的结尾添加新的子节点
>     * removeChild() :删除（并返回）当前节点的指定子节点
>     * replaceChild() :用新节点替换一个子节点
>   * 属性:parentNode 返回节点的父节点
>
>
>
>