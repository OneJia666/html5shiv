＃HTML5 Shiv

HTML5 Shiv支持使用传统Internet Explorer中的HTML5分段元素，并为Internet Explorer 6-9，Safari 4.x（和iPhone 3.x）和Firefox 3.x提供基本的HTML5样式。

###这些文件是做什么的？

####`html5shiv.js`
*这包括基本的`createElement（）`shiv技术，以及针对IE6-8的`document.createElement`和`document.createDocumentFragment`的monkeypatches。它也适用于IE6-9，Safari 4.x和FF 3的HTML5元素[基本样式]（https://github.com/aFarkas/html5shiv/blob/51da98dabd3c537891b7fe6114633fb10de52473/src/html5shiv.js#L216-220）。 X。

####`html5shiv-printshiv.js` 
*这包括以上所有内容，以及允许在IE 6-8中打印HTML5元素并包含子元素的机制。

###现在谁可以生气？

HTML5 Shiv由[Alexander Farkas]（https://github.com/aFarkas/），[Jonathan Neal]（https://twitter.com/jon_neal）和[Paul Irish]（https://twitter.com）维护/ paul_irish），有许多来自[John-David Dalton]（https://twitter.com/jdalton）的贡献。它也与[Modernizr]（http://modernizr.com/）分发。

如果您在这些实施中遇到任何问题，您可以在这里举报！:)

有关HTML5 Shiv和所有参与制作的人的全文，请阅读[HTML5 Shiv的故事]（http://paulirish.com/2011/the-history-of-the-html5-shiv/） 。

##安装

###使用[Bower]（http://bower.io/）

`bower安装html5shiv --save-dev`

这会将最新版本的HTML5 shiv克隆到项目根目录下的“bower_components”目录中，并创建或更新指定项目依赖关系的文件“bower.json”。

将HTML5 shiv包含在页面的<head>中，在条件注释中以及任何样式表之后。

```HTML
<！ -  [if lt IE 9]>
	<script src =“bower_components / html5shiv / dist / html5shiv.js”> </ script>
<！[ENDIF]  - >
```

###手动安装
从这个版本库
下载并提取[最新的zip包]（https://github.com/aFarkas/html5shiv/archive/master.zip），并复制dist / html5shiv.js和dist / html5shiv-printshiv这两个文件.js`到你的项目中。然后将其中的一个包含到你的`<head>`中。

## HTML5 Shiv API

HTML5 Shiv是一个简单的插入式解决方案。在大多数情况下，不需要配置HTML5 Shiv或使用HTML5 Shiv提供的方法。

###`html5.elements`选项

`elements`选项是一个空格分隔的字符串或数组，它描述了shiv元素的** full **列表。另见`addElements`。

**在包含`html5shiv.js`之前配置`elements` **

```JS
//创建一个全局的html5选项对象
window.html5 = {
  '元素'：'标识部分客户' 
};
```
**包含`html5shiv.js`后配置`elements` **

```JS
//更改html5shiv选项对象 
window.html5.elements ='标记栏目customelement';
//并重新调用`shivDocument`方法
html5.shivDocument（文件）;
```

###`html5.shivCSS`

如果`shivCSS`被设置为`true`，则HTML5 Shiv会将基本样式（主要是display：block）添加到截面元素（如section，article）中。在大多数情况下，网页作者应该在他的正常样式表中包含这些基本样式，以确保在没有JavaScript的情况下支持较旧的浏览器（即Firefox 3.6）。

`shivCSS`默认是true，只有在包含html5shiv.js之前，才可以设置为false： 

```JS
//创建一个全局的html5选项对象
window.html5 = {
	'shivCSS'：错误
};
```

###`html5.shivMethods`

如果`shivMethods`选项设置为true（默认），HTML5 Shiv将在Internet Explorer 6-8中重写`document.createElement` /`document.createDocumentFragment`，以允许动态DOM创建HTML5元素。 

已知问题：如果使用重写的createElement方法创建元素，则此元素将返回文档片段作为其“parentNode”，但通常应为“null”。如果一个脚本依赖于这个行为，`shivMethods`应该被设置为`false`。
注意：jQuery 1.7+为Internet Explorer 6-8实现了自己的HTML5 DOM创建修复程序。如果所有脚本（包括第三方脚本）都使用jQuery的操作和DOM创建方法，则可能需要将此选项设置为“false”。

**在包含`html5shiv.js`之前配置`shivMethods` **

```JS
//创建一个全局的html5选项对象
window.html5 = {
	'shivMethods'：假
};
```
**包含`html5shiv.js`后配置`elements` **

```JS
//更改html5shiv选项对象 
window.html5.shivMethods = false;
```

###`html5.addElements（newElements [，document]）`

`html5.addElements`方法将元素列表扩展为shiv。newElements参数可以是空格分隔的列表或数组。

```JS
//将元素列表扩展为shiv
html5.addElements（'element content'）;
```

###`html5.createElement（nodeName [，document]）`

即使`shivMethods`设置为false，`html5.createElement`方法也会创建一个shived元素。

```JS
var container = html5.createElement（'div'）;
//容器被移动，所以我们可以使用`innerHTML`来添加HTML5元素
container.innerHTML ='<section>这是一节</ section>';
```

###`html5.createDocumentFragment（[document]）`

即使`shivMethods`设置为false，`html5.createDocumentFragment`方法也会创建一个shived文档片段。

```JS
var fragment = html5.createDocumentFragment（）;
var container = document.createElement（'div'）;
fragment.appendChild（容器）;
//片段被移动，所以我们可以使用`innerHTML`来添加HTML5元素
container.innerHTML ='<section>这是一节</ section>';
```

## HTML5 Shiv已知问题和限制

- `shivMethods`选项（覆盖`document.createElement`）和`html5.createElement`方法创建元素，这些元素没有断开连接并有一个父节点（参见问题＃64）
- 克隆节点问题目前还没有被HTML5 Shiv解决。HTML5元素可以动态创建，但不能在所有情况下克隆。
--HTML5 Shiv的printshiv版本必须改变打印样式和整个DOM进行打印。对于复杂的网站和/或大量的打印样式，这可能会导致性能和/或样式问题。可能的解决方案可能是HTML5 Shiv 的[htc-branch]（https://github.com/aFarkas/html5shiv/tree/iepp-htc），它使用另一种技术来实现Internet Explorer 6-8的打印样式。

###其他的HTML5元素项目呢？

- 该项目的原始概念和社区合作故事在[HTML5 Shiv的历史]中描述（http://paulirish.com/2011/the-history-of-the-html5-shiv/）。
- Jon Neal 撰写的[IEPP]（https://code.google.com/p/ie-print-protector）解决了原始`html5shiv`的打印错误。它被合并到`html5shiv`中。
-  ** Shimprove **，2010年4月，修补cloneNode和createElement后来被合并到`html5shiv`
-  JD Barlett于2010年8月推出的** innerShiv **，在DOM中动态添加新的HTML5元素。[jQuery添加支持]（http://blog.jquery.com/2011/11/03/jquery-1-7-released/），使innerShiv冗余和`html5shiv`解决相同的问题，所以该项目是完成。
-  Google代码中的** html5shim **和** html5shiv **网站由Remy Sharp维护，并且是这个`html5shiv`项目的相同分发点。
-  ** Modernizr **由与`html5shiv`相同的人开发，可以包含在modernizr.com创建的任何定制版本中的最新版本
- 这个`html5shiv`回购现在包含了上述库追求的所有边缘案例的测试，并且在开发和生产中都经过了广泛的测试。 

[html5shiv的详细更新日志]（https://github.com/aFarkas/html5shiv/wiki）可用。

###为什么叫做* shiv *？
从[John Resig]（https://github.com/jeresig）
这个术语** shiv ** [originate]（http://ejohn.org/blog/html5-shiv/），被认为是使用用于俚语的意思，*用作刀形武器的尖锐物体，用于Internet Explorer。说实话，John可能打算使用[shim]（http://en.wikipedia.org/wiki/Shim_ ( computing ））这个词，它在计算中意味着*应用程序兼容性解决方法*。大多数熟悉Internet Explorer的开发人员不是纠正错误，而是欣赏视觉图像。那孩子呢，是[词源]（https://en.wikipedia.org/wiki/Etymology）。