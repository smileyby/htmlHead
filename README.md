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

## 360 Google Chrome Frame

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

## viewport

viewport 可以让布局在移动端浏览器上显示的更好，通常会写：

```html

	<meta name="viewport" content="width=device-width, initial-scale=1.0">

```

width=device-width会导致 iPhone5添加到主屏后以WebApp 全屏模式打开页面时会出现黑边[http://ooxx.me/ios-webapp-viewport-meta.orz](http://ooxx.me/ios-webapp-viewport-meta.orz)

content 参数：
*	width viewport 宽度（数值/device-width）
*	height viewport 高度（数值/device-height）
*	initial-scale 初始化缩放比例
*	maximum-scale 最大缩放比例
*	minimum-scale 最小缩放比例
*	user-scalable 是否允许用户缩放（yes/no）
*	minimal-ui IOS 7.1 beta 2中新增属性，可以在页面加载时最小化上下状态栏。这是一个布尔值，可以直接这样写：

```html

	<meta name="viewport" content="width-device-width, initial-scale=1, minimal-ui">

```

如果你的网站不是响应式的，请不要使用initial-scale或者禁用缩放。

```html

	<meta name="viewport" content="width=device-width, user-scalable=yes">

```

相关连接：[非响应式设计的viewport](https://www.qianduan.net/non-responsive-design-viewport/)

适配Iphone 6 和 iPhone 6plus则需要些：

```html

	<meta name="viewport" content="width=375">
	<meta name="viewport" content="width=414">

```

大部分4.7~5寸的安卓设备的viewport宽度设为360px，iPhone 6上确是375px，大部分5.5寸安卓设备（比如三星Note）的viewport宽为400， iPhone 6plus 上是414px。

## ios设备

添加到主屏后的标题 （ios6 新增）

```html

	<meta name="apple-mobile-web-app-title" content="标题">

```

是否开启WebApp全屏模式

```html

	<meta name="apple-mobile-web-app-capable" content="yes">

```

设置状态栏的背景颜色

```html

	<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
	<!-- 设置状态栏的背景颜色，只有在‘apple-mobile-web-app-capable content=yes’ 时才生效 -->

```

只有在 `apple-mobile-web-app-capable` `content=yes`时生效

content参数：
*	default默认值
*	black状态栏背景是黑色
*	blcak-translucent 状态栏背景是黑色半透明。如果设置为default或black，网页内容从状态栏底部开始。如果设置为black-translucent，网页内容充满真个屏幕，顶部会被状态栏遮挡。

禁止数字识别自动生成为电话号码

```html

	<meta name="format-detection" content="telephone=no"> 
	<!-- 禁止数字自动识别为电话号码 -->

```

## ios图标

rel参数：apple-touch-icon 图片自动处理成圆角和高光等效果。apple-touch-icon-precomposed 禁止系统自动添加效果，直接显示设计院图。 iPhone和iTouch， 默认57*57像素，必须有：

```html

	<link rel="apple=touch-icon-precomposed" href="/apple-touch-icon-57*57-precomposed.png">
	<!-- iPhone 和 iTouch 默认57*57像素，必须有 -->

```

iPad， 72*72像素，可以没有，但推荐有

```html

	<link rel="apple-touch-icon-precomposed" sizes="72*72" href="/apple-touch-icon-72x72-precomposed.png">

```

Retina iPhone 和 Retina iTouch，114x114 像素，可以没有，但推荐有

```html

	<link rel="apple-touch-icon-precomposed" sizes="114x114" href="/apple-touch-icon-114x114-precomposed.png" /> 
	<!-- Retina iPhone 和 Retina iTouch，114x114 像素，可以没有，但推荐有 -->

```

Retina iPad，144x144 像素，可以没有，但推荐有

```html

	<link rel="apple-touch-icon-precomposed" sizes="144x144" href="/apple-touch-icon-144x144-precomposed.png" /> 
	<!-- Retina iPad，144x144 像素，可以没有，但推荐有 -->

```

IOS 图标大小在iPhone 6 plus上是180×180，iPhone 6 是120x120。 适配iPhone 6 plus，则需要在<head>中加上这段

```html

	<link rel="apple-touch-icon-precomposed" sizes="180x180" href="retinahd_icon.png">

```

## ios启动画面

官方文档：[https://developer.apple.com/library/ios/qa/qa1686/_index.html](https://developer.apple.com/library/ios/qa/qa1686/_index.html)

iPad的启动画面是不包括状态栏区域的。

iPad竖屏768*1004 （标准分辨率）

```html

	<link rel="apple-touch-startup-image" size="768*1004" href="/splash-screen-768x1004.png">
	
```

iPad 竖屏 1536x2008（Retina）

```html

	<link rel="apple-touch-startup-image" sizes="1536x2008" href="/splash-screen-1536x2008.png" />
	
```

iPad 横屏 1024x748（标准分辨率）

```html

	<link rel="apple-touch-startup-image" sizes="1024x748" href="/Default-Portrait-1024x748.png" />
	
```

iPad 横屏 2048x1496（Retina）

```html

	<link rel="apple-touch-startup-image" sizes="2048x1496" href="/splash-screen-2048x1496.png" />
	
```

iPhone 和 iPod touch 的启动画面是包含状态栏区域的。

iPhone/iPod Touch 竖屏 320x480 (标准分辨率)

```html

	<link rel="apple-touch-startup-image" href="/splash-screen-320x480.png" />
	
```

iPhone/iPod Touch 竖屏 640x960 (Retina)

```html

	<link rel="apple-touch-startup-image" sizes="640x960" href="/splash-screen-640x960.png" />
	
```

iPhone 5/iPod Touch 5 竖屏 640x1136 (Retina)

```html

	<link rel="apple-touch-startup-image" sizes="640x1136" href="/splash-screen-640x1136.png" />
	
```

添加智能 App 广告条 Smart App Banner（iOS 6+ Safari）

```html

	<meta name="apple-itunes-app" content="app-id=myAppStoreID, affiliate-data=myAffiliateData, app-argument=myURL">
	
```

iPhone 6对应的图片大小是750×1294，iPhone 6 Plus 对应的是1242×2148 。

```html

	<link rel="apple-touch-startup-image" href="launch6.png" media="(device-width: 375px)">

	<link rel="apple-touch-startup-image" href="launch6plus.png" media="(device-width: 414px)">
	
```

## Windows 8

windows8贴条颜色

```html

	<meta name="msapplication-TileColor content="#000"">
	
```

windows 8磁铁图标

```html

	<meta name="msapplication-TileImage" content="icon.png">

```

## rss订阅

```html

	<link rel="alternate" type="application/rss+xml" title="RSS" href="/rss.xml">

```
## favicon icon

```html

	<link rel="shortcut icon" type="image/ico" href="/favicon.ico">

```

比较详细的favicon介绍可以参考[https://github.com/audreyr/favicon-cheat-sheet](https://github.com/audreyr/favicon-cheat-sheet)

## 移动端meta

```html

	<meta name="viewport" content="width=device-width, inital-scale=1, user-scalable=no">
	<meta name="apple-mobile-web-app-capable" content="yes">
	<meta name="apple-mobile-web-app-status-bar-style" content="black">
	<meta name="format-detection" content="telephone=no, email=no">
	<meta name="apple-mobile-web-app-capable" content="yes"> <!-- 删除苹果默认的工具栏和菜单栏 -->
	<meta name="apple-mobile-web-app-status-bar-style" content="no"> <!-- 苹果工具栏颜色 -->
	<meta name="format-detection" content="telphone=no, email=no"> <!-- 忽略页面中的数字识别为电话，忽略email识别 -->
	
	<!-- 启用360浏览器的极速模式 -->
	<meta name="renderer" content="webkit"> 
	
	<!-- 避免IE使用兼容模式 -->
	<meta http-equiv="X-UA-Compatible" content="IE-edge">
	
	<!-- 针对手持设备优化，主要针对一些老的不识别viewport的浏览器，比如黑莓 -->
	<meta name="HandheldFriendly" content="true">
	
	<!-- 微软的老式浏览器 -->
	<meta name="MobileOptimized" content="320">
	
	<!-- uc强制竖屏 -->
	<meta name="screen-orientation" content="portiait">
	
	<!-- QQ强制竖屏 -->
	<meta name="x5-orientation" content="portiait">

	<!-- uc强制全屏 -->
	<meta name="full-screen" content="yes">
	
	<!-- QQ强制全屏 -->
	<meta name="x5-fullscreen" content="true">
	
	<!-- UC 应用模式 -->
	<meta name="browsermode" content="application">
	
	<!-- QQ应用模式 -->
	<meta name="x5-page-mode" content="application">

	<!-- windows phone 点击无高光 -->
	<meta name="msapplication-tap-highlight" content="no">

```
更多的meta标签参考：
*	[http://www.iacquire.com/blog/18-meta-tags-every-webpage-should-have-in-2013](http://www.iacquire.com/blog/18-meta-tags-every-webpage-should-have-in-2013)

参考文章：
*	[https://github.com/yisibl/blog/issues/1](https://github.com/yisibl/blog/issues/1)
*	[https://gist.github.com/paddingme/6182708733917ae36331](https://gist.github.com/paddingme/6182708733917ae36331)
*	[http://www.uisdc.com/ios8-ten-new-feature](http://www.uisdc.com/ios8-ten-new-feature)







	



