# 前端规范文档

### 代码规范

js/css/html规范参考自：http://front-end-standards.com/    
会对其进行筛选并加以细化  
建议参考谷歌代码规范  
[谷歌JavaScript代码规范](https://google.github.io/styleguide/javascriptguide.xml)  


### 架构说明
使用支持模块化/组件化的webapp工程化框架：  
scrat(类似seajs与requirejs,原作者在之前的基础上进行了改装)  
工具网址:http://scrat.io/  


### 好处
1. 模块化开发，且将html/css/js放置在一起，易于维护，便于公用
2. 支持版本管理，自动化打包，新版本发布后用户可以直接看到效果，没有缓存影响
3. 将静态资源进行了合并，减少请求，性能优化
4. 前后端分离，职责分离
5. 增加路由，横向导航菜单，支持网址链接

### 开发环境

```
 项目名称/
├── component_modules(第三方组件库)
├── components(模块化业务/定制组件库)
│   ├── common(公用组件)
│   │   ├── accordionMenu(手风琴菜单)
│   │   ├── common(错误捕获，请求处理等工用代码，较混论，待改造)
│   │   ├── config(服务端请求配置，前后端分离调试用)
│   │   ├── datatableUX(表格控件封装)
│   │   ├── datepickerUX(日期控件封装)
│   │   ├── modalCreator(模态框控件封装)
│   │   ├── footer(底部版权说明组件)
│   │   ├── monitor(前端监视器，暂未使用)
│   │   ├── navBar(横向导航菜单组件)
│   │   ├── navTitle(global-nav头，品牌、换肤、用户，目前只有集团页使用，集团页与项目页稍有不同)
│   │   ├── summaryInfo(右侧面板)
│   │   ├── treeList(三级菜单)
│   │   ├── updatePassword(前端监视器，暂未使用)weather
│   │   ├── monitor(前端监视器，暂未使用)
│   │   ├── weather(天气组件)
│   │   ├── ......（还有更多可待提取到这里）
│   ├── group（集团页面相关组件）
│   │   ├── img(图片)
│   │   ├── module(横向主菜单对应的各个模块)
│   │   │   ├── ..........
│   │   │   ├── systemManage
│   │   │   │   ├── memu(三级菜单，一般用于配置）
│   │   │   │   │   ├── alarManage
│   │   │   │   │   ├── ..........
│   │   │   │   ├── systemManage.js(入口)
│   │   │   │   ├── systemManage.html(模板)
│   │   │   ├── ..........
│   │   ├── reportmodal(各种弹出框，告警、事件等)
│   │   ├── group.css(集团页面总样式)
│   │   ├── group.handlebars(集团页面html模板)
│   │   ├── group.js(集团组件代码)
│   ├── login（登录页面相关组件）
│   │   ├── img(图片)
│   │   ├── login.css(登录页面总样式)
│   │   ├── login.handlebars(登录页面html模板)
│   │   ├── login.js(登录组件代码)
│   ├── project（项目页面相关组件）
│   │   ├── img(图片)
│   │   ├── module(横向主菜单对应的各个模块)
│   │   ├── reportmodal(各种弹出框，告警、事件等)
│   │   ├── project.css(项目页面总样式)
│   │   ├── project.handlebars(项目页面html模板)
│   │   ├── project.js(项目组件代码)
│   ├── theme(主题组件)
│   │   ├── theme.css(主题样式)
│   │   ├── theme.js(主题组件代码)
├── server(nodeJS服务端，c#端该朝这个方向改进，此外还可用来做前后端分离)
└── view（非模块化代码，入口）
│   │   ├── img(图片)
│   │   ├── lib(静态组件库)
│   │   │   ├── common(暂时无法改造或归类的我先放这里了)
│   │   │   ├── scrat(模块化组件，类似seaJS)
│   │   │   ├── static(照搬以前的static)
│   │   │   ├── reset(浏览器样式重置，跨浏览器有用，像bootstap这样的框架已解决问题)
│   │   │   ├── group(集团全局性质的代码或样式)
│   │   │   ├── project(项目全局性质的代码或样式)
│   │   │   ├── handlebars(模板引擎)
│   │   │   ├── lib(静态代码请求合并，打包至lib.js)
│   │   ├── group.js(集团入口)
│   │   ├── group.html(集团页)
│   │   ├── login.js(登录入口)
│   │   ├── login.html(登录页)
│   │   ├── project.js(项目入口)
│   │   ├── project.html(项目页)
├── .gitignore(忽略，git版本管理配置用)
├── .build.sh(git相关，代码提交)
├── .travis(项目初始化时用)
├── component(组件配置，需遵循组件规范，可深入了解下)
├── fis-conf(scat基于的工程化框架，百度生产，需要深入)
├── LICENSE(证书，忽略)
├── package(NodeJS模块说明，忽略)
└── README.md(项目说明，写你想写)
```

### 开发方式
1. 安装 Nodejs
2. 安装 scrat
```
npm install scrat -g 
```

3.Dos下 cd /path/to/前端开发环境
```
scrat server start
```
然后，在浏览器中访问 http://127.0.0.1:5000  

4. 其它  
 + 热调: scrat release -wL  
 + 发布: scrat release -d ./目录



### 发布目录结构(参考：http://scrat.io/#!/quick-start)
```
../output
  ├─ public
  │  ├─ c (模块化资源部署目录)
  │  │  ├─ scrat-site
  │  │  │  └── 0.1.0
  │  │  ├─ scrat-team-type
  │  │  │  └── 0.1.0
  │  │  ├─ sems
  │  │  │  └── 0.1.0
  │  └─ sems (非模块化资源部署目录)
  │     └─ 0.1.0
  │        ├── group.js
  │        ├── group.html
  │        └── lib
  │        └── ...
  ├─ server (nodejs服务器部署目录，忽略)
  └─ package.json (nodejs依赖描述，忽略)
```

### 发布方式（略显复杂，待改进）
1. 暂时需要手动将/public/sems/版本号(如0.1.0)/下的group.html、project.html替换为group.aspx、project.aspx(这块可咨询我:))  
2. 在发布目录拷贝views、public至HYD.E3.UI目录下
3. 拷贝HYD.E3.UI目录下的images文件至/public/sems/版本号(如0.1.0)/下
4. 设置/public/sems/版本号(如0.1.0)/login.html为起始页
5. F5运行


### 开发工具推荐
- sublime3  
- visual studio code  

### TODO
1. c#后端支持合并请求(原生只带有nodejs版本)
2. 前后端彻底分离，现在用的group.aspx与project.aspx仍依赖与后端，此外，发布略显麻烦，还需要拷贝图片至相关路径(可咨询我)
3. 后端路由配置  

### 问题
1. 样式问题严重，首页之前使用display切换显示，现在采用模板渲染方式（详情参考代码）  
2. css代码在一个样式文件里边，需要进行模块化改造，不然也不好维护 
3. 前后端分离调试，还需对服务端进行改造，特别是登录状态保持那一块！
4. ToXls.aspx分离
5. xamp文件分离

