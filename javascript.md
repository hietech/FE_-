# JAVASCRIPT 规范

## JS 文件结构
    ---/js/
    |---- /libs/plugin-1/       使用到的js插件1
    |---- /libs/plugin-2/       使用到的js插件2
    |---- /libs/plugin-3/       使用到的js插件3
    |---- script.js             单独书写的js
    |---- plugins.js            调用的plugins汇总
    |---- juqery-1.9.x.min.js   调用jq库文件

* JS 换行缩进：采用 4 空格
* 结束行需添加分号`;`
* jQuery变量要求首字符为 `$`, 私有变量:首字符为`_`; 尽量避免全局变量.
* 避免使用 eval()，setTimeOut使用调用函数，考虑重绘，回流 操作对页面影响  参看：[reflows，repaints]
* JS调试使用`console.log()`及`console.dir()`进行，避免使用弹出框，线上版需要注释所有调试代码
* JS压缩混淆工具: [JS Compressor]  如果使用了压缩，需要留 `name-src.js`在同路径供今后修改使用

### jQuery Call
    <!-- Grab Google CDN jQuery. fall back to local if necessary -->
    <script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js"></script>
    <script>!window.jQuery && document.write('<script src="js/jquery-1.7.2.min.js"><\/script>')</script>
### jQuery Plugin

* IE对HTML5标签支持，以及浏览器特性检测：[Modernizr] & [html5shiv]
* <del>IE6 PNG 图片支持：[DD_belatedPNG]</del>
* 定制&统一 浏览器的滚动条样式：[jquery-scroll] & [Lionbars]
* hover提示效果文字：[bootstrap-tooltips] & [tipsy]
* 滚动条跟随nav效果：[bootstrap-scrollspy]
* 提示冒泡文字：[grumble.js]
* 导航栏过渡效果：[lavalamp]
* 移动设备的滚动效果：[iscroll 4]
* Mac OS Lion 风格的滚动条：[Lionbars]
* 弹性SlideShow：[kwicks for jQuery]
* 瀑布流：[isotope]
* 抖动效果：[jQ shake]
* LightBox：[fancyBox]
* KenDo UI：[KenDo UI]
* textarea自适应高度：[elastic]
* 提示区域 & 提示层：[noty]
* 浮动话题泡：[jQuery grumble]
* 旋转进度：[jQuery Knob]

### JSON格式规范
参考[JSON Style Guide翻译]，原版：[Google JSON Style Guide]

