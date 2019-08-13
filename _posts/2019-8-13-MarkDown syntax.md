#  Typora Mark-Down Syntax

### 块元素 Block Elements

#### 1.段落和行结束 Paragraph and Line Breaks

> 使用html 的 </br>

#### 2.标题 Headers

> 标题前面有几个# 号就代表几号标题 一共有6级标题

#### 3.引用 Blockquotes

> 现在这行就是引用 就是按 "  >  " 加一个空格 即可形成灰色的字体，我一般用于具体解释标题内容

#### 4.列表 Lists

> 使用 * 即可 是无序列表，1. 是有序列表

#### 5. 代码块 Code Block

>  **```<语言> 回车**  

```java
public static void main(string[]){
   //关键字会高亮
}
```

#### 6.表格 Tables

>使用  " | first con| second con|" 创建两列

| first con | second con |
| :-------- | ---------- |
|           |            |

#### 7.脚注 Foot-Notes

> this is soupman[^1]

[^1]: soupman is my name

#### 8. 横线 Horizontal Rules

> **- - -**

#### 9. 加粗 Strong

> ** 文字 ** 注意：文字和星号应无空格

#### 10.强调 Emphasis

> *文字 * 注意：文字和星号应无空格

#### 11.代码 Code

> 文中要加入代码时：**` static ‘**  ：注意static 右边符号应该与左边一致方向方能有效
>
> `public static int function(){}`

#### 12.删除线 Strike-through

> ~~文字~~  ：在文字左右都添加~~

#### 13.下划线 Underlines

> 使用html的u标签    <u>文字</u>

#### 14.上标和下标 super-script and sub-script

> 下标： 在需要下标文字左右两边各加一个 ~        H~2~O
>
> 上标： 在需要上标文字左右两边各加一个 ^        X^3^

#### 15.高亮 Highlight

> 在文字左右两边各添加两个 ==
>
> ==soupman==

#### 16.链接 Links

> this is my github website [mansoup](https://github.com/mansoup)
>
> **[]()**  :在方括号添加文字，圆括号添加链接地址

#### 17.图片 Images

在链接格式基础上在左边添加一个感叹号！

>![my HeadPic](/images/HeadPic.jpg)
>
>使用html方式
>
><img src="/images/HeadPic.jpg" width="20%">



#### 18.快捷键 Key-board shortcut

> * 标题：ctrl+数字
> * 表格：ctrl+t
> * 生成目录：[TOC]按回车
> * 选中一整行：ctrl+l
> * 选中单词：ctrl+d
> * 选中相同格式的文字：ctrl+e
> * 搜索：ctrl+f
> * 代码块：ctrl+alt+f
> * 加粗：ctrl+b
> * 倾斜：ctrl+i
> * 下划线：ctrl+u
> * 删除线：alt+shift+5
> * 插入图片：直接拖动到指定位置即可或者ctrl+shift+i
> * 插入链接：ctrl+k
