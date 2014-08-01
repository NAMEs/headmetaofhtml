HTML的`<head></head>`介绍和使用

----------  

## 1.http-equiv属性 ##

见过最多的这一句

 `<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />`

html5可以简写为

`<meta charset="utf-8"/>`

http-equiv属性还有以下属性：

- Content-Language

	设置网页语言

	`<meta  http-equiv="content-Language" contect="zh-CN">`

- Refresh

	指定的时间刷新页面

	<meta http-equiv="refresh" content="300">

- set-cookie

	设定页面cookie过期时间，操作cookie跟js操作cookie类似
	
 	 `<meta http-equiv="set-cookie" contect="cookievalue=xxx; expires=Wed, 12 Dec 2012 12:12:12 GMT; path=/">
`

- last-modified：页面的最后生成时间



- location：重定向到另一个网址


- window-target：指定了这个属性的iframe，会在加载这个iframe的页面窗口打开。


- date：指定页面创建的日期。


- Pragma：设置是否缓存网页



- Expires



- 设定网页Cache过期时间
	
 	`<meta http-equiv="expires" contect="Wed, 12 Dec 2012 12:12:12 GMT">`



- cache-control：设置文档的缓存机制。值如下：

	public：浏览器和缓存服务器都可以缓存页面信息
	
	private：只缓存在浏览器端
	
	no-cache：浏览器和缓存服务器都不应该缓存页面信息
	
	no-store：请求和响应的信息都不应该被存储在对方的磁盘系统中

----------

    	
    <meta http-equiv="pragram" content="no-cache"> 
    
    禁止浏览器从本地缓存中调阅页面。 
    网页不保存在缓存中，每次访问都刷新页面。 
    
    <meta http-equiv="cache-control" content="no-cache, must-revalidate"> 
    
    同上面意思差不多，必须重新加载页面 
    
    <meta http-equiv="expires" content="0"> 
    
    网页在缓存中的过期时间为0，一旦网页过期，必须从服务器上重新订阅。

##  2.name属性  ##
> name 属性提供了名称/值对中的名称，可以自定义，所以搜索引擎商以及浏览器厂商都有针对自家浏览器定义的name属性。



- IOS相关

apple-touch-icon：

    创建桌面图标和启动画面，在meta标签中指定它的值可以使得你的网页在保存至主屏时，显示为自定义的icon，而不是网页的缩略图
    <link rel="apple-touch-icon" href="/custom_icon.png"/>
    <link rel="apple-touch-icon" href="touch-icon-iphone.png" />
    <link rel="apple-touch-icon" sizes="72x72" href="touch-icon-ipad.png" />
    <link rel="apple-touch-icon" sizes="114x114" href="touch-icon-iphone4.png" />
				
> apple-touch-startup-image:

    给网页声明启动画面，类似原生app。但是被声明的图片对于iphone和itouch 大小只能是 320 x 460 ，其他大小的都无效。但是同样你可以通过sizes 来进行多设备适配。
    <y;link rel="apple-touch-startup-image" href="/startup.png">
    //for iphone Retina Display high
    <y;link rel="apple-touch-startup-image" sizes="640x960" href="img/splash-screen-640x960.png" />
    //for iPad Landscape
    <y;link rel="apple-touch-startup-image" sizes="1024x748" href="img/splash-screen-1024x748.png" />
    //for iPad Portrait
    <y;link rel="apple-touch-startup-image" sizes="768x1004" href="img/splash-screen-768x1004.png" />
				

> PS：ios2.1以上支持

    apple-mobile-web-app-title
    添加到主屏时的标题
    
    <y;meta name="apple-mobile-web-app-title" content="标题">
    				
    apple-mobile-web-app-status-bar-style
    隐藏状态栏，default 为默认参数
    
    <y;meta name="apple-mobile-web-app-status-bar-style" content="black" /> 
				
> PS：ios2.1以上支持

    apple-mobile-web-app-capable
    设置一个web应用程序是否在全屏模式下运行。
    
    <y;meta name="apple-mobile-web-app-capable" content="yes" />
				
> PS：ios2.1以上支持

    format-detection
    忽略将页面中的数字识别为电话号码
    
    <meta name="format-detection" content="telephone=no"  /> 
				
> PS：ios1.0以上支持

viewport

    觉得此属性是移动开发最重要的，所以自成一章。viewport 属性视能告诉浏览器如何规范的渲染网页。
    
    width：viewport 的宽度（范围从223 到10,000）
    height：viewport 的高度
    （范围从223 到10,000）
    
    initial-scale：初始的缩放比例（范围从>0 到10）
    minimum-scale：允许用户缩放到的最小比例（范围从>0 到10）
    maxnim-scale：允许用户缩放到的最大比例（范围从>0 到10）
    user-scalable：用户是否可以手动缩 (no,yes)
    minimal-ui：ios 7.1新增页面加载时可以最小化上下状态栏
    PS：如在移动端如下设置 <meta name="viewport" content="width=320;initial-scale=1.0;">则是告诉了浏览器网页在320px下显示是最合适的，那么移动端浏览器则会在设备宽内显示320px的内容，在移动端上320px代表的是设备宽度所能容纳的像素数而不是实际宽度
    

- window8

    msapplication-TileColor:
    设置Windows 8 磁贴颜色
    
    <meta name="msapplication-TileColor" content="#ff0"/> 
    				
    msapplication-TileImage:
    设置Windows 8 磁贴图标
    
    <meta name="msapplication-TileImage" content="icon.png"/>
				
- 搜索引擎相关

    date：
    定义网页生成时间
    
    <meta name="date" content="2008-07-12T20:50:30+00:00" />
    				
    keywords：
    定义网页关键词
    
    <meta name="keywords" content="HTML js css" />
    				
    description：
    定义网页简短描述
    
    <meta name="description" content="语义,各平台提供兼容性,提高用户浏览速度,优化产品的交互,提供可扩展的接口" />
    				
    author：
    定义网页作者
    
    <meta name="author" content="http://html5jscss.com/" />
    				
    copyright：
    定义网页版权
    
    <meta name="copyright" content="© http://www.dreamdu.com" />
    				
    robots
    定义网页搜索引擎索引方式，robotterms是一组使用逗号(,)分割的值，通常有如下几种取值：none，noindex，nofollow，all，index和follow。
    

    `<meta name="robots" content="robotterms" />`
	
## 3.其他  ##

 以及360首创的浏览器内核控制

    <meta name="renderer" content="webkit|ie-comp|ie-stand">
 强制使用浏览器的最高版本模式进行渲染
> 
    <meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1" /> 
			
> 这个 meta 标签主要是避免用户安装了IE9，但浏览器却以IE7模式进行渲染的问题。