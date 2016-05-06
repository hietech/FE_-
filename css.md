# CSS规范

### CSS文件结构
    --- ../css/
     |---- css/libs/reset.css                  CSS reset文件
     |---- … …
     |---- css/images/                         主 CSS-sprite 图片
     |---- css/style.css                       主 CSS 样式表
     |---- … …
     |---- css/images/xxx/sprite.png           xxx 的 CSS-sprite 图片
     |---- css/xxx-style.css                   xxx 的 样式表

### CSS(含Less) 文件结构
    --- ../css/
     |---- css/libs/reset.less            CSS reset文件
     |---- css/libs/elements.less         Less 函数复用文件
     |---- … …
     |---- css/images/                         主 CSS-sprite 图片
     |---- css/style.less                      主样式Less
     |---- css/style.css                       less -> css 自动生成
     |---- … …
     |---- css/images/xxx/sprite.png           xxx 的 CSS-sprite 图片
     |---- css/xxx-style.less                  xxx 的 Less
     |---- css/xxx-style.css                   less -> css 自动生成

### 使用Less
在 `.less`文件头部引入 [reset.less] & [elements.less]，之后调用如下属性传参即可，具体使用说明见 -> [Lesselements] 官方文档

    @import "libs/reset.less";
    @import "libs/elements.less";

    .gradient
    .bw-gradient
    .bordered
    .drop-shadow
    .rounded
    .border-radius
    .opacity
    .transition-duration
    .rotation
    .scale
    .transition
    .inner-shadow
    .box-shadow
    .columns
    .translate

### CSS reset
CSS reset 文件使用：[reset.css] 或 [reset.less]

* reset文件用于重设各个浏览器的默认样式方案，解决其引起的耦合问题。
* 也可使用 `.clearfix` 清除浮动

### CSS注释格式约定
    /*
    @name: Drop Down Menu
    @description: Style of top bar drop down menu.
    @require: reset.css
    @author: Andy Huang(andyahung@geekpark.net)
    */

_其中，@require为可选项_

* CSS换行制表：使用 2 <del>或4</del> 个空格，而非\[Tab\]
* 书写格式：
    * CSS名称+冒号+属性
    如：`.box1 {float:left;}`
    * 建议保留`{`左侧空格，字体名用`\`包含
    如：`.box1,.box2,.box3 {font-family:Courier,'Courier New';}`
    * 避免中文，或使用转义，推荐前者
    如：`font-family: "Microsoft YaHei";` `font-family:\5fae\8f6f\96c5\9ed1;`

### CSS各属性的排列顺序：不做硬性要求
_如：以下2种顺序均可_

    .box {
      /* 顺序1 */
      background: none repeat scroll 0 0 transparent;
      bottom: 11px;
      position: relative;
      width: 22px;
      z-index: 33;
    }
    .box {
      /* 顺序2 */
      z-index: 33;
      width: 22px;
      bottom: 11px;
      background: transparent none repeat scroll 0 0 ;
      position: relative;
    }

### CSS嵌套规则
    /* 推荐嵌套层级 */
    .ui-icon-rarr{}
    .ui-icon-larr{}
    .ui-title{}
    .ui-nav .ui-list{}
    .ui-table .ui-list{}

    /* 不推荐 */
    .ui-icon-rarr{}
    .ui-icon-larr{}
    .ui-title{}
    .ui-list{}
    .ui-nav{}

### CSS格式化
勿格式化，保留下面这种格式，增加可读性和可维护性，后期后台程序(如：PHP/Python)会将CSS压缩成 **一行** 输出：

    .box{
      /* 勿格式化，增加可读性 */
      background: none repeat scroll 0 0 transparent;
      bottom: 11px;
      position: relative;
      width: 22px;
      z-index: 33;
    }
