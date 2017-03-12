HTML head 头标签
===============

HTML head头部分的标签，元素有很多，设计到浏览器对网页的渲染，seo等等，而哥哥浏览器内核以及哥哥国内浏览器厂商都有些自己的标签元素，这就造成了很多差异性。移动互联网时代，head头部结构，移动端的meta元素，线的更为重要。了解每个标签的意义，写出满足自己需求的head头标签，是本文的目的。

## DOCTYPE

DOCTYPE（Document Type），该声明位于文档中最前面的为止，处于html标签之前，此标签告知浏览器文档该使用哪种html或者xhtml规范。

DID（Document Type Definition）声明<!DOCTYPE>开始，不区分大小写，前面没有任何内容，如果有其他内容（空格除外）会是浏览器在IE下开启怪异模式（quirks mode）渲染网页。公共DTD，名称格式为注册//组织//类型 标签//语言，注册指组织是否由国际标准化组织（ISO）注册，+表示是，-表示不是。组织即组织名称，如：W3C。类型一般是DTD。标签是指定公开文本描述，即对所有的公开文本的唯一描述性名称，后面可复发i版本号。最后语言是DTD语言的ISO639语言标识符。如：EN表示英文，ZH表示中文。XHTML1.0可声明三种DTD类型，分别表示严格版本，过渡版本，以及基于框架的HTML文档。

*	html4.01 strict

```html

	<!DOCTYPE HTML PUBLIC "-//W3C//dtd HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">

```

*	html 4.01 Transitional

```html

	<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

```

*	html4.01 Frameset

```html

  	<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">

```

*	最新HTML5退出更加简洁的书写，它向前后兼容，推荐使用

```html

	<!doctype html>

```

在HTML中doctype有两个主要目的。

*	对文档进行有效验证。
	* 它告诉用户代理和校验器这个文档是按照什么DTD写的。这个动作是被动的，每次页面加载时，浏览器并不会下载DTD并检查合法性，只有当手动校验页面时开启用。
*	决定浏览器的呈现模式
	* 对于实际操作，通知浏览器读取文档是用那种解析算法。如果没有写，则浏览器则根据自身的规则对代码进行解析，可能会严重影响html排版布局。浏览器有三种方式解析html文档。* 非怪异（标准）模式 * 部分怪异（近乎标准）模式。	

## charset

声明文档使用的字符编码

```html

	<meta charset="utf-8">

```

html5之前网页中会这样写：

```html

	<meta http-equic="Content-Type" content="text/html; charset=utf-8">

```

这两个是等效的，具体可阅读[<meta charset='utf-8'> vs <meta http-equiv='Content-Type'>](<meta charset='utf-8'> vs <meta http-equiv='Content-Type'>)建议使用较短的，易于记忆。

## lang属性

简体中文

```html

	<html lang="zh-cmn-Hans">

```

繁体中文

```html

	<html lang="zh-cmn-Hant">

```

为什么lang="zh-cmn-Hans"为不是我们通常用的lang="zh-CN"，请阅读[页头部的声明应该是用 lang=”zh” 还是 lang=”zh-cn”](https://www.zhihu.com/question/20797118?utm_source=weibo&utm_medium=weibo_share&utm_content=share_question&utm_campaign=share_sidebar)

## 优先使用IE最新版本和Chrome

```html

	<meta http-equiv="X-UA-Compatible" content="IE=dege,chrome=1">

```

## 360是哟个Google Chrome Frame

```html

	<meta name="render" content="webkit">

```

360浏览器就会读取到这个标签后，立即切换对应的急速内核，另外为了保险起见再加入:

```html

	<meta http=equiv="X-UA-Compatible" content="IE=eDGE,CHROME=1">

```

这样写可以达到的效果是如果安装了Google Chrome Frame ，则使用GCF来渲染页面，如果没有安装GCF，则使用最版本的IE内核进行渲染。

相关链接：[浏览器内核控制 Meta 标签说明文档](http://se.360.cn/v6/help/meta.html)

## 百度禁止转码

通过百度手机打开网页时，百度可能会你的网页进行转码，脱下你的衣服，往你身上贴狗皮膏药的广告，为此可在head内添加：

```html
	
	<meta http-equiv="Cache-Control" content="no-siteapp">

```
## SEO 优化部分

*	页面标题title标签（head头部必须）

```html

	<title>your title</title>

```


*	页面关键词 keywords

```html

	<meta name="keywords" content="your keywords">

```


*	页面标题title标签（head头部必须）

```html

	<title>your title</title>

```


*	页面描述内容 description

```html

	<meta name="description" content="your description">

```


*	定义网页作者 author

```html

	<meta name="author" content="author,email address">

```

*	定义网页搜索引擎索引方式，robotterms 是一组使用英文逗号「,」分割的值，通常有如下几种取值：none，noindex，nofollow，all，index和follow

```html

	<meta name="robots" content="index,follow">

```

未完待续[http://fex.baidu.com/blog/2014/10/html-head-tags/](http://fex.baidu.com/blog/2014/10/html-head-tags/)







	



