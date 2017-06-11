##学习markdown

OmniMarkupPreviwer：实时在浏览器中预，而MarkdownPreview是需要手动生成的和F5的。如果双屏的话，应该具有不错的体验。快捷键如下：

+ Ctrl+Alt+O: Preview Markup in Browser.
+ Ctrl+Alt+X: Export Markup as HTML.
+ Ctrl+Alt+C: Copy Markup as HTML.


####重要符号
```
#  （1-6个）                                    标题

底线（= 最高阶、减号- 第二阶）                   标题

+、-、* 后加空格                                无序列表

1.(数字+句点)                                   有序列表

反引号 （ ` ）                                  行内代码块

缩进4个空格或是一个制表符                       代码区块

引用符号：>

一行中三个以上星号、减号、底线                   分隔线

[文字](地址 '可选title')					     链接（行内式）

[文字][参考链接]  [参考链接]:<url> 'title'      链接（参考式）

星号（*）和底线（_）                            强调（二个 * 或 _ 变加粗）

![Alt text](/path/img.jpg "Optional title")    图片（行内式）

![Alt text][参考名称]  [参考名称]:url title     图片 (参考式)
 
<链接地址>                                      自动链接
```


###标题
Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。
类 Setext 形式是用底线的形式，利用 = （最高阶标题）和 减号- （第二阶标题）

setext标题（=）
=================

setext标题2（-）
----------------------
类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶，例如：

```
# 这是 H1

## 这是 H2

###### 这是 H6
```

>你可以选择性地「闭合」类 atx 样式的标题，这纯粹只是美观用的，若是觉得这样看起来比较舒适，你就可以在行尾加上 #，而行尾的 # 数量也不用和开头一样（行首的井字符数量决定标题的阶数）：


```
# 这是 H1 #

## 这是 H2 ##

### 这是 H3 ######
```
##Markdown 支持有序列表和无序列表

无序列表使用星号、加号或是减号作为列表标记：
```
*   Red
*   Green
*   Blue
```
等同于：
```
+   Red
+   Green
+   Blue
```
也等同于：
```
-   Red
-   Green
-   Blue
```
有序列表则使用数字接着一个英文句点：
```
1.  Bird
2.  McHale
3.  Parish
```
很重要的一点是，你在列表标记上使用的数字并不会影响输出的 HTML 结果，上面的列表所产生的 HTML 标记为：
```
<ol>
<li>Bird</li>
<li>McHale</li>
<li>Parish</li>
</ol>
```

这是一个普通段落：

	这是一个代码区块。

分隔线

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：
	
```
* * *

***

*****

- - -

---------------------------------------
```
###自动链接

	[123](http://baidu.com 'title显示')
	<123@163.com>

[123](http://baidu.com 'title显示')	
<123@163.com>

###图片

允许两种样式：行内式和参考式

	行内式语法：

	![Alt text](/path/to/img.jpg)
	![Alt text](/path/to/img.jpg "optional title")

详细叙述如下：

+ 一个惊叹号 !
+ 接着一个方括号，里面放上图片的替代文字
+ 接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上 选择性的 'title' 文字。

![图片](timg.jpg "jfg")

	参考式语法:
	![Alt text][参考名称]
	[参考名称]: timg.jpg "jfg"

	![Alt text][id]    //[id]是图片参考的名称，图片参考的定义方式：
	[id]: url/to/image  "Optional title attribute"

![Alt text][refname]
[refname]: timg.jpg "jfg"

###开启行内代码

如果要标记一小段行内代码，你可以用反引号把它包起来（`）

	Use the `printf()` function.
Use the `printf()` function.

**开启css语法代码块**
```css
.a{
	font-size:5px;
}
```
**开启js语法代码块**
```js
 function test(a){
  alert("hello");
 }
```
**开启java语法代码块**
```java
  public class Hello{
	   private int a=0;
	   public Hello(){}
	   public static void main(String[] args){
			System.out.println("Hello Java");
	   }
  }
```

如果要在代码区段内插入反引号，你可以用多个反引号来开启和结束代码区段：

	``There is a literal backtick (`) here.``

这段语法会产生：

<p><code>There is a literal backtick (`) here.</code></p>



###强调

**nihao**

Markdown 使用星号（*）和底线（_）作为标记强调字词的符号，被 * 或 _ 包围的字词会被转成用em标签包围，用两个 * 或 _ 包起来的话，则会被转成strong标签，例如：

	*single asterisks*

	_single underscores_

	**double asterisks**

	__double underscores__

	un*frigging*believable

_single underscores_

**double asterisks**

un*frigging*believable

 但是**如果你的 * 和 _ 两边都有空白的话，它们就只会被当成普通的符号**。

如果要在文字前后直接插入普通的星号或底线，你可以用反斜线：

\*this text is surrounded by literal asterisks\*

###链接

链接文字都是用 [方括号] 来标记

要建立一个**行内式**的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：

	This is [an example](http://example.com/ "Title") inline link.
	[This link](http://example.net/) has no title attribute.

This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.

**参考式**的链接是在链接文字的括号后面再接上另一个方括号，而在第二个方括号里面要填入用以辨识链接的标记：

	This is [an example][id] reference-style link.


你也可以选择性地在两个方括号中间加上一个空格：

	This is [an example] [id] reference-style link.
接着，在文件的任意处，你可以把这个标记的链接内容定义出来：

	[id]: http://example.com/  "Optional Title Here"
	
	链接网址也可以用尖括号包起来：
	[id]: <http://example.com/>  "Optional Title Here"

[id]: <http://example.com/>  "Optional Title Here"
This is [an example][id] reference-style link.

链接辨别标签可以有字母、数字、空白和标点符号，但是并**不区分大小写**，因此下面两个链接是一样的：

	[link text][a]
	[link text][A]

**隐式链接**标记功能让你可以省略指定链接标记，这种情形下，链接标记会视为等同于链接文字，要用隐式链接标记只要在链接文字后面加上一个空的方括号，如果你要让 "Google" 链接到 google.com，你可以简化成：

	[Google][]
然后定义链接内容：

	[Google]: http://google.com/
由于链接文字可能包含空白，所以这种简化型的标记内也许包含多个单词：

	Visit [Daring Fireball][] for more information.
然后接着定义链接：

	[Daring Fireball]: http://daringfireball.net/

链接的定义可以放在文件中的任何一个地方，我比较偏好直接放在链接出现段落的后面，你也可以把它放在文件最后面，就像是注解一样。

下面是一个参考式链接的范例：

	I get 10 times more traffic from [Google] [1] than from
	[Yahoo] [2] or [MSN] [3].

	  [1]: http://google.com/        "Google"
	  [2]: http://search.yahoo.com/  "Yahoo Search"
	  [3]: http://search.msn.com/    "MSN Search"