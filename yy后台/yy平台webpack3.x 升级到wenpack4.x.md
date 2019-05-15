## yy平台webpack3.x 升级到wenpack4.x





1. 先升级所有相关插件和loader。dependencies下不用升级。其他最好都升到最新版本
2. 修改配置文件，一些被淘汰的插件和loader删除(破坏性修改，且行且珍惜)
3. build目录下until.js,build.js等js文件修改

- 需要升级的插件



| 插件                               | 功能                                                         | 目前版本 | 目标升级版本 |
| ---------------------------------- | ------------------------------------------------------------ | -------- | ------------ |
| autoprefixer                       | 将使用基于当前浏览器流行度和属性支持的数据为您应用前缀       | 6.7.7    | 9.5.1        |
| babel-eslint                       | eslint 自定义解析器                                          | 7.2.3    | 10.0.1       |
| babel-loader                       | 用于webpack的babel模块加载器                                 | 7.1.4    | 8.0.5        |
| babel-plugin-import                | 用于babel的组件模块化导入插件。                              | 1.6.2    | 1.11.0       |
| copy-webpack-plugin                | 使用webpack复制文件&&目录                                    | 4.0.1    | 5.0.3        |
| cross-env                          | 运行跨平台设置和使用环境变量的脚本                           | 3.1.2    | 5.2.0        |
| css-loader                         | css加载模块                                                  | 0.25.0   | 2.1.1        |
| eslint                             | 一个基于AST的JavaScript模式检查器。                          | 3.18.0   | 5.16.0       |
| eslint-config-standard             | JavaScript标准样式 - ESLint可共享配置                        | 6.2.1    | 12.0.0       |
| eslint-friendly-formatter          | Eslint的简单格式化程序/报告者(友好)                          | 3.0.0    | 4.0.1        |
| eslint-loader                      | Eslint加载模块                                               | 1.6.1    | 2.1.2        |
| eslint-plugin-html                 | 一个ESLint插件，用于lint和修复HTML文件中包含的内联脚本。     | 2.0.1    | 5.0.3        |
| eslint-plugin-promise              | promises                                                     | 3.4.2    | 4.1.1        |
| eslint-plugin-standard             | ESlint Plugin for the Standard Linter                        | 2.0.1    | 4.0.0        |
| eslint-plugin-vue                  | Vue.js的官方ESLint插件                                       | 4.5.0    | 5.2.2        |
| exports-loader                     | 导出webpack的加载器模块                                      | 0.6.4    | 0.7.0        |
| file-loader                        | 用于webpack的文件加载器模块                                  | 0.9.0    | 3.0.1        |
| Friendly-errors-webpack-plugin     | 识别某些类别的webpack错误，并清理，聚合和优先级，以提供更好的开发人员体验 | 1.6.1    | 1.7.0        |
| html-webpack-plugin                | 简化HTML文件的创建                                           | 2.28.0   | 3.2.0        |
| http-proxy-middleware              | HTTP代理中间件                                               | 0.17.4   | 0.19.1       |
| less-loader                        | Less loader for webpack                                      | 2.2.3    | 4.1.0        |
| optimize-css-assets-webpack-plugin | 优化\最小化CSS                                               | 3.1.1    | 5.0.1        |
| postcss-loader                     | 使用[PostCSS](https://webpack.js.org/)处理CSS的[webpack的](https://postcss.org/)加载器 | 0.13.0   | 3.0.0        |
| progress-bar-webpack-plugin        | 进度条                                                       | 1.9.0    | 1.12.1       |
| sass-loader                        | Sass loader for webpack                                      | 6.0.7    | 7.0.1        |
| script-loader                      | 用于webpack的脚本加载器模块                                  | 0.7.0    | 0.7.2        |
| style-loader                       | Style loader module for webpack                              | 0.13.1   | 0.23.1       |
| url-loader                         | A loader for webpack which transforms files into base64 URIs. | 0.5.8    | 1.1.2        |
| webpack                            | webpack                                                      | 3.11.0   | 4.31.0       |
| webpack-merge                      | webpack合并                                                  | 4.1.0    | 4.2.1        |
|                                    |                                                              |          |              |
|                                    |                                                              |          |              |
|                                    |                                                              |          |              |
|                                    |                                                              |          |              |

- 已被的淘汰插件需要被替换

| 插件                           | 功能                                                       | 目前版本 | 替换后插件名称和版本                                         |
| ------------------------------ | ---------------------------------------------------------- | -------- | ------------------------------------------------------------ |
| babel-core                     | babel编译核心                                              | 6.26.0   | @babel/core ^7.4.4                                           |
| babel-plugin-transform-runtime | 外部引用辅助函数和内置函数，自动填充代码而不会污染全局变量 | 6.22.0   | @babel/plugin-transform-runtime ^7.4.4                       |
| babel-polyfill                 | 提供完整ES2015 +环境所需的polyfill                         | 6.23.0   | @babel/polyfill ^7.4.4                                       |
| babel-preset-env               | 为每个环境预设的Babel。                                    | 1.6.1    | @babel/preset-env ^7.4.4                                     |
| babel-preset-es2015,           | 为es2015预设的Babel                                        | 6.14.0   | 废弃                                                         |
| babel-preset-stage-2           | es规范惨案stage-2预设的Babel                               | 6.17.0   | 废弃                                                         |
| gulp-util                      | gulp插件的实用功能                                         | 3.0.7    | 废弃 [备注](https://medium.com/gulpjs/gulp-util-ca3b1f9f9ac5) |
| opn                            | 打开URL，文件，可执行文件等内容。跨平台                    | 5.1.0    | open ^6.3.0                                                  |
| opo                            |                                                            | 1.0.0    | 废弃                                                         |
| webpack-hot-middleware         | 热更新中间价                                               | 2.18.0   | 2.24.4                                                       |
| webpack-dev-middleware         | Webpack的开发中间件                                        | 1.10.2   | 3.6.2                                                        |
|                                |                                                            |          |                                                              |
|                                |                                                            |          |                                                              |
|                                |                                                            |          |                                                              |
|                                |                                                            |          |                                                              |



- 无需改动 对工程影响不大的插件

| 插件                         | 功能                                                         | 目前版本 | 最新版本 |
| ---------------------------- | ------------------------------------------------------------ | -------- | -------- |
| chalk                        | 改变控制台样式                                               | 2.3.0    | 2.3.0    |
| connect-history-api-fallback | 通过指定索引页面代理请求的中间件，对使用HTML5 History API的单页面应用程序很有用。(exprss 的中间件 对打包无影响) | 1.3.0    | 1.3.0    |
| eventsource-polyfill         | 用于W3C EventSource的浏览器polyfill                          | 0.9.6    | 0.9.6    |
| express                      | [Node.js](http://nodejs.org/) Web 框架                       | 4.15.2   | 4.16.4   |
| extract-text-webpack-plugin  | 将包中的文本提取到文件中                                     | 3.0.2    | 3.0.2    |
| font-awesome                 | 字体和CSS框架                                                | 4.7.0    | 4.7.0    |
| js-cookie                    | 一个简单，轻量级的JavaScript API，用于处理cookie             | 2.1.4    | 2.2.0    |
| node-notifier                | Node.js模块，用于在本机Mac，Windows（post和pre 8）和Linux（或Growl作为后备）上发送通知 | 5.1.2    | 5.4.0    |
| node-sass                    | Wrapper around libsass                                       | 4.10.0   | 4.11.0   |
| on-build-webpack             | [Webpack](http://webpack.github.io/) plugin that gives ability to add callback after build. | 0.1.0    | 0.1.0    |
| ora                          | 优雅的终端微调器                                             | 0.3.0    | 3.4.0    |
| Qs                           | 查询字符串解析和字符串化库，增加了一些安全性。               | 6.4.0    | 6.7.0    |
| serve-favicon                | Node.js middleware for serving a favicon.                    | 2.3.0    | 2.5.0    |
| stylus-loader                | Stylus loader for webpack                                    | 2.3.1    | 3.0.2    |
| tinymce-imageupload          | Tinymce富文本图片上传插件                                    | 1.0.5    | 1.0.5    |
| uppercamelcase               | 将短划线/点/下划线/空格分隔的字符串转换为UpperCamelCase      | 1.1.0    | 3.0.0    |
| vinyl-buffer                 | [gulp-streamify](http://github.com/nfroidure/gulp-streamify)的替代方法 | 1.0.0    | 1.0.1    |
|                              |                                                              |          |          |
|                              |                                                              |          |          |



- gulp 相关插件

| 插件              | 功能                                 | 目前版本 | 最新版本 |
| ----------------- | ------------------------------------ | -------- | -------- |
| gulp              | 基于流的自动化构建工具               | 3.9.1    | 4.0.2    |
| gulp-autoprefixer | Css 前缀                             | 3.1.0    | 6.1.0    |
| gulp-clean-css    | 压缩css                              | 2.0.8    | 4.0.0    |
| gulp-if           | 有条件地过滤内容                     | 2.0.0    | 2.0.2    |
| gulp-imagemin     | 压缩图片                             | 3.0.1    | 5.0.3    |
| gulp-less         | Less for Gulp                        | 3.0.5    | 4.0.1    |
| gulp-rename       | Rename files                         | 1.2.2    | 1.4.0    |
| gulp-sequence     | 按顺序运行一系列依赖gulp任务         | 0.4.6    | 2.2.1    |
| gulp-shell        | 一个方便的gulp命令行界面             | 0.5.2    | 0.7.0    |
| gulp-uglify       | 压缩js                               | 1.5.3    | 3.0.2    |
| gulp-vsftp        | 通过SSH上传文件                      | 0.7.8    | 0.7.8    |
| gulp-vsftppro     | 通过SSH上传文件                      | 0.0.6    | 0.0.6    |
| gulp.spritesmith  | 将一组图像转换为spritesheet和CSS变量 | 6.2.1    | 6.9.0    |
|                   |                                      |          |          |

- 工程开发依赖相关插件

| 插件                 | 功能                                                         | 目前版本 | 最新版本 |
| -------------------- | ------------------------------------------------------------ | -------- | -------- |
| less                 | CSS 预处理语言，它扩展了CSS 语言                             | 2.7.2    | 3.9.0    |
| stylus               | CSS 预处理语言，它扩展了CSS 语言                             | 0.54.5   | 0.54.5   |
| zepto                | zepto                                                        | 1.2.0    | 1.2.0    |
| @tinymce/tinymce-vue | 这个包是一个薄的包装`tinymce`，使它更容易在Vue应用程序中使用。 | 2.0.0    | 2.0.0    |
| axios                | Ajax                                                         | 0.16.2   | 0.18.0   |
| clipboard            | 复制到剪贴板                                                 | 1.7.1    | 2.0.4    |
| echarts              | 图表和可视化库                                               | 3.5.3    | 4.2.1    |
| element-ui           | vue组件库                                                    | 2.5.4    | 2.8.2    |
| json2csv             | 使用列标题和正确的行结尾将json转换为csv。 可以用作模块和命令行 | 3.11.2   | 4.5.1    |
| moment               | 一个轻量级JavaScript日期库，用于解析，验证，操作和格式化日期 | 2.23.0   | 2.24.0   |
| popper.js            | 计算元素的位置，使其可以将其定位在给定的参考元素附近         | 0.6.4    | 1.14.3   |
| shelljs              | Node.js的Unix shell命令                                      | 0.7.8    | 0.8.3    |
| vue                  | Vue                                                          | 2.4.4    | 2.6.10   |
| vue-clipboards       | 指令将文本复制或剪切到剪贴板                                 | 1.2.4    | 1.2.4    |
| vue-router           | [Vue.js](http://vuejs.org/)的官方路由器                      | 2.5.3    | 3.0.6    |
| vue-ueditor          |                                                              | 0.1.3    |          |
| vuex                 | Vue.js的集中状态管理                                         | 2.3.1    | 3.1.1    |
| vuex-router-sync     | 将vue-router的当前$ route同步为vuex store的状态的一部分      | 4.1.2    |          |
|                      |                                                              |          |          |

- 新增插件

| 插件               | 功能                                                         | 版本  |
| ------------------ | ------------------------------------------------------------ | ----- |
| webpack-dev-server | 将[webpack](https://webpack.js.org/)与提供实时重新加载的开发服务器一起使用。这应该仅用于**开发**。 | 3.3.1 |
|                    |                                                              |       |
|                    |                                                              |       |

