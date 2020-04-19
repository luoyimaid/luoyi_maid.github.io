---
title: 详解web标准
date: 2017-12-02 14:48:04
tags: html+CSS
---

- #### WEB标准是一系列标准的集合，网页主要由三部分组成：结构（Structure）、表现（Presentation）和行为（Behavior）。对应的标准也分三方面：结构化标准语言主要包括XHTML和XML，表现标准语言主要包括CSS，行为标准主要包括对象模型（如W3C DOM）、ECMAScript等。
![引用块内容](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9nc3MzLmJkc3RhdGljLmNvbS83UG8zZFNhZ194STRraEdrcG9XSzFIRjZoaHkvYmFpa2UvYzA9YmFpa2U4MCw1LDUsODAsMjYvc2lnbj0yYzBhNTMwNWYyMWZiZTA5MDg1M2NiNDYwYTA5Njc1Ni9iZDNlYjEzNTMzZmE4MjhiZjFkZmYxOTBmZDFmNDEzNDk2MGE1YWMwLmpwZw?x-oss-process=image/format,png)

### **1.结构标准**
* **可扩展标记语言（XML）**

    #### 和[HTML](https://baike.baidu.com/item/HTML)一样，XML同样来源于标准通用标记语言，可扩展标记语言和标准通用标记语言都是能定义其他语言的语言。XML最初设计的目的是弥补HTML的不足，以强大的扩展性满足网络信息发布的需要，后来逐渐用于[网络数据](https://baike.baidu.com/item/%E7%BD%91%E7%BB%9C%E6%95%B0%E6%8D%AE)的转换和描述。

* **可扩展超文本标记语言([XTHML](https://baike.baidu.com/item/XHTML))**
    #### 目前推荐遵循的是W3C于2000年1月26日推荐XML1.0。XML虽然数据转换能力强大，完全可以替代HTML，但面对成千上万已有的站点，直接采用XML还为时过早。因此，我们在HTML4.0的基础上，用XML的规则对其进行扩展，得到了XHTML。简单的说，建立XHTML的目的就是实现HTML向XML的过渡

### **2.表现标准**
- #### [层叠样式表](https://baike.baidu.com/item/CSS/5457?fromtitle=%E5%B1%82%E5%8F%A0%E6%A0%B7%E5%BC%8F%E8%A1%A8&fromid=524980)（CSS）。目前推荐遵循的是万维网联盟（W3C）于1998年5月12日推荐CSS2。W3C创建CSS标准的目的是以CSS取代HTML表格式布局、帧和其他表现的语言。纯CSS布局与结构式XHTML相结合能帮助设计师分离外观与结构，使站点的访问及维护更加容易。

### **3.行为标准**
* #### ECMAScript
- #### ECMAScript 是 ECMA 制定的标准[脚本语言](https://baike.baidu.com/item/%E8%84%9A%E6%9C%AC%E8%AF%AD%E8%A8%80)(javaScript),目前遵循的是ECMAScript 262

* #### 文档对象模型
- #### [文档对象模型](https://baike.baidu.com/item/%E6%96%87%E6%A1%A3%E5%AF%B9%E8%B1%A1%E6%A8%A1%E5%9E%8B)（DOM）。根据[W3C DOM规范](http://www.w3.org/DOM/)，DOM是一种与浏览器，平台，语言的接口，使得你可以访问页面其他的标准组件。简单理解，DOM解决了Netscaped的Javascript和Microsoft的Javascript之间的冲突，给予web设计师和开发者一个标准的方法，让他们来访问他们站点中的数据、脚本和表现层对象。

### **4.代码标准**
* #### 必须结束标记
    #### XHTML要求有严谨的结构，所有标签必须关闭。如果是单独不成对的标签，在标签最后加一个"/"来关闭它。
    #### 例如:`<br />`
    #### 例如：`<img height="80" alt="网页设计师" src="../images/logo_w3cn_200x80.gif" width="200" />`

* #### 小写元素和属性名
    #### XHTML对大小写是敏感的，`<title>`和`<TITLE>`是不同的标签。XHTML要求所有的标签和属性的名字都必须使用小写。
    #### 大小写夹杂也是不被认可的，通常dreamweaver自动生成的属性名字`onMouseOver`也必须修改成`onmouseover`。

* #### 标记都必须合理嵌套
    #### 例如：`<p><b></b></p>`,就是说，一层一层的嵌套必须是严格对称。

* #### 属性必须括起来
    #### 例如:`<height=80>`必须修改为：`<height="80">`
    #### 特殊情况：你需要在属性值里使用双引号，你可以用"，单引号可以使用`&apos;`，例如：`<alt="say&apos;hello&apos;">`

* #### 特殊符号用编码表示
    #### 1. <，不是标签的一部分，都必须被编码为`&lt;` ;
    #### 2. >，不是标签的一部分，都必须被编码为`&gt;`;
    #### 3. &，不是实体的一部分，都必须被编码为`&amp;`;
    #### 4. ` `,不是实体的一部分，都必须被编码为`&nbsp;`

* #### 给所有属性赋值
    #### XHTML规定所有属性都必须有一个值，没有值的就重复本身。
    #### 例如：`<td nowrap> <input type="checkbox" name="shirt" value="medium"checked>`
    #### 必须修改为：`<td nowrap="nowrap"> <input type="checkbox" name="shirt"value="medium" checked="checked">`

* #### 在注释中不使用的符号
    #### “--”只能发生在XHTML注释的开头和结束，也就是说，在内容中它们不再有效。例如下面的代码是无效的:`<!--这里是注释-----------这里是注释-->`

### **5.测试标准**
#### **（1）标准测试的内容**
    #### **1. 页面校验**
    #### **2.CSS文档校验**
    #### **3.XHTML 1.0 标准**
    #### **4.W3C标准测试**
    #### **测试时一定要有文件类别宣告还有指定文件编码，才能顺利进行测试动作，开始打造一个标准的网站！**
    #### `<meta http-equiv="Content-Type" content="text/html; charset=gb2312" />`

#### **（2）W3C标准测试使用说明**
* #### XHTML 1.0文件类别宣告的正确写法 (不可小写)
    #### 过度标准（Transitional）公共标识符称为:"-//W3C//DTD XHTML1.0Transitional//EN"。
    `<!DOCTYPE htmlPUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN">`
    #### 框架标准（Frameset）公共标识符称为：“-//W3C//DTD XHTML 1.0 Frameset//EN”。
    `<!DOCTYPE htmlPUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN">`
    #### 严格标准（Strict） 公共标识符称为：“-//W3C//DTD XHTML 1.0 Strict//EN”。
    `<!DOCTYPE htmlPUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN">`

* #### 所有网页头文件都必须改为标准格式
```
<head>
<meta
       http-equiv="content-type"
       content="text/html; charset=gb2312" />
<meta http-equiv="content-language" content="zh-cn" />
<meta name="keywords" content="..." />
<meta name="description" content="..."/>
<title>...</title>
</head>
```

* #### 不允许使用`target="_blank";`
    在HTML4.01可以使用`target="_blank"`,但XHTML1.0是不被允许的.

```
function 外部链接()		//unicode javascript
{
      if (!document.getElementsByTagName) return;
      var anchors = document.getElementsByTagName("a");
      for (var i=0; i<anchors.length; i++)
      {
            var anchor = anchors;
            if (anchor.getAttribute("href") &&
            anchor.getAttribute("rel") == "external")
            anchor.target = "_blank";
      }
} 
window.onload = 外部链接;
```
    #### 你可以把它保存成一个.js文件(比如外部链接.js)，然后通过外部联接方法调用：
`<script type="text/javascript" src="外部链接.js"></script>`

* #### XHTML 1.0要求所有的标签必须关闭
    #### 所有没有成对的空标签必须以 />结尾,例如：
	` <hr />`
    `<input type="text" name="name" />`

* #### 所有标签元素名都使用小写
    #### 错误 `<HTML> <TITLE> <HEAD> <BODY>`
    #### 正确` <html> <title> <head> <body>`

* #### 同一个id选择器不可同时使用
    #### 一个网页中id="xx"同一个选择器不能重复使用,若需要重复请用class="xx"

* #### 标签必须是一对
    例如：`<p></p>`

* #### 正确标签顺序

* #### JavaScript写法
    #### W3C标准必须为程式指定类型type=text/javascript,所以要写为
    #### ` <scripttype="text/javascript">`或者
    #### `<script language="javascript" type="text/javascript">`
    #### 载入外部.js独立档案的写法
    `<script type="text/javascript" src="script.js"></script>`

* #### 绝对不可省略单引号或者双引号
    #### 错误: `<img src=bg.gif width=140 height=30 alt=text />`
    #### 正确:` <img src="bg.gif" width="140" height="30" alt="text" />`

* #### 图片标签加上文字说明`alt="文字说明"`
    `<img src="bg.gif" height="50" border="0" alt="说明文字" />`

* #### 背景音乐不允许使用 `bgsound `标签
    正确写法如下，然后通过外部链接方法调用
	```
	var MSIE=navigator.userAgent.indexOf("MSIE");
	var NETS=navigator.userAgent.indexOf("Netscape");
	var OPER=navigator.userAgent.indexOf("Opera");
	if((MSIE>-1) || (OPER>-1)) {
	document.write("<BGSOUND SRC=背景音乐地址 LOOP=INFINITE>");
	} else {
	document.write("<EMBED SRC=背景音乐地址 AUTOSTART=TRUE ");
	document.write("HIDDEN=true VOLUME=100 LOOP=TRUE>");
	}
	```	

* #### 不允许使用框架标签
    #### 用js通过外链引入页面
	```
	function ifr(url,w,h){
		document.write('<iframe id="ifr" name="ifr" width="'+w+'" height="'+h+'" border="0" frameborder="0" scrolling="no" src="'+url+'"></iframe>');}
	```
	
* #### 注解文字不可包含"--"符号
    #### 错误` <!-- OEC--SPACE -->`
    #### 正确 `<!-- OECSPACE -->`

* #### 正确使用[CSS样式表](https://baike.baidu.com/item/CSS/5457?fromtitle=CSS%E6%A0%B7%E5%BC%8F%E8%A1%A8&fromid=224735)

* #### 非标签部分以编码表示

* #### 所有属性都必须有值

### **6.优点**
### *(1)对于访问者*
    **文件下载与页面显示速度更快。**
    **内容能被更多的用户所访问（包括失明、视弱、色盲等残障人士）。**
    **内容能被更广泛的设备所访问(包括屏幕阅读机,手持设备,搜索机器人,打印机,电冰箱等)。**
    **用户能够通过样式选择定制自己的表现界面。**
    **所有页面都能提供适于打印的版本。**

### *(2)对于网站所有者*
    **更少的代码和组件，容易维护。**
    **带宽要求降低（代码更简洁），成本降低。举个例子：当 ESPN.com 使用 CSS改版后，每天节约超过两兆字节（terabytes）的带宽。**
    **更容易被搜寻引擎搜索到。**
    **改版方便，不需要变动页面内容。**
    **提供打印版本而不需要复制内容。**
    **提高网站易用性。在美国，有严格的法律条款（Section 508）来约束政府网站必须达到一定的易用性，其他国家也有类似的要求。**

### **7.误区**
    **不为通过校验才标准化**
        web标准的本意是实现内容(结构)和表现分离，就是将样式剥离出来放在单独的css文件中。这样做的好处是可以分别处理内容和表现，也方便搜索和内容的再利用。
        W3C校验仅仅是帮助你检查XHTML代码的书写是否规范，css的属性是否都在CCS2的规范内。代码的标准化仅仅是第一步，不是说通过的校验，我的网页就标准化了。我们不是为了虚名，或者向别人炫耀：“看我的页面通过了校验”而去标准化，我们的目的是为了使自己的网页设计工作更有效率，为了缩小网页尺寸，为了能够在任何浏览器和网络设备中正常浏览。

    **不用传统表格思维来套div**

    **不必每块内容都建id**
        我们知道内容都是有结构的(如果不明白，请[点击阅读](http://www.w3cn.org/article/tips/2004/43),理解表现和结构相分离 ,相同的结构的内容我们可以用同一个样式来定义，比如相同级别的标题、正文、图片。对于多次引用的样式可以用class来定义，不需要每个都用id；另外也不是说一定要用，你完全可以用别的来代替，同样都是块级元素，一样有盒模型的七个参数，仅仅方便浮动。


