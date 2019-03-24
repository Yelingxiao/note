## HTML

* **[`DOCTYPE`是什么？](#DOCTYPE是什么)**

* **[`<meta>`标签](#<meta>标签)**

* **[HTML5的基本构件(building block)](#HTML5的基本构件building-block)**

* **[如何制作快速加载的HTML页面](#如何制作快速加载的HTML页面)**

#####  `DOCTYPE`是什么？

`DOCTYPE`是“document type”的缩写。在[HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML)中，文档类型声明是必要的。所有的文档的头部，你都将会看到"`<!DOCTYPE html>`" 的身影。这个声明的目的是防止浏览器在渲染文档时，切换到我们称为“[怪异模式(兼容模式)](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Quirks_Mode_and_Standards_Mode)”的渲染模式。“`<!DOCTYPE html>`" 确保浏览器按照最佳的相关规范进行渲染，而不是使用一个不符合规范的渲染模式。

关键点：文档类型声明 渲染模式 标准模式 文档头部

[[↑] 回到顶部](#HTML)



#####  `<meta>`标签

> 标签提供关于HTML文档的元数据。元数据不会显示在页面上，但是对于机器是可读的。它可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 web 服务。



| **属性**      | **值**                                                       | **描述**                            |
| :------------ | ------------------------------------------------------------ | ----------------------------------- |
| http-equiv    | content-type / expire / refresh / set-cookie                 | 把content属性关联到HTTP头部。       |
| name          | author / description / keywords / generator / revised / others | 把 content 属性关联到一个名称。     |
| content(必选) | some text                                                    | 定义用于翻译 content 属性值的格式。 |



**Example**

```html
<!-- In HTML5 申明字符编码为utf-8-->
<meta charset="utf-8">

<!-- `width=device-width` 会导致 iPhone 5 添加到主屏后以 WebApp 全屏模式打开页面时出现黑边  -->
<meta name="viewport" content="width=device-width, initial-scale=1.0,maximum-scale=1.0, user-scalable=no"/>

<!-- 它已经过时了。使用 <html> 元素上全局的 lang 属性来替代它.  -->
<meta http-equiv="Content-Language"content="zh-cn"/> 
```



设置某些<meta>`标签有利于**SEO**(Search Engine Optimization 搜索引擎优化)

[[↑] 回到顶部](#HTML)



##### HTML5的基本构件(building block)



>  **HTML5** 是定义 [HTML](https://developer.mozilla.org/zh-CN/docs/HTML) 标准的最新的版本。



* **语义**：能够让你更恰当地描述你的内容是什么。
* **连通性**：能够让你和服务器之间通过创新的新技术方法进行通信。
* **离线 & 存储**：能够让网页在客户端本地存储数据以及更高效地离线运行。
* **多媒体**：使 video 和 audio 成为了在所有 Web 中的一等公民。
* **2D/3D 绘图 & 效果**：提供了一个更加分化范围的呈现选择。
* **性能 & 集成**：提供了非常显著的性能优化和更有效的计算机硬件使用。
* **设备访问 Device Access**：能够处理各种输入和输出设备。
* **样式设计**: 让作者们来创作更加复杂的主题吧！

参考：[MDN HTML5](https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/HTML5)

[[↑] 回到顶部](#HTML)



##### 如何制作快速加载的HTML页面

**Tips**

* 减少页面体积
* 最小化页面数量
* 减少域名查找
* 缓存重用的内容
* 高效排列页面组件
* 减少内联脚本数量
* 使用现代化css和合法标记
* 给内容分块
* 制定图片和表格的大小
* 合理的选择user-agent
* 尽可能选择使用async和defer



>defer: (延迟)这个布尔属性被设定用来通知浏览器该脚本将在文档完成解析后，触发 `DOMContentLoaded` 事件前执行。如果缺少 `src` 属性（即内嵌脚本），该属性不应被使用，因为这种情况下它不起作用。对动态嵌入的脚本使用 `async=false` 来达到类似的效果
>
>async: (异步)该布尔属性 html5属性 指示浏览器是否在允许的情况下异步执行该脚本。该属性对于内联脚本无作用 (即没有**src**属性的脚本）。

参考：[MDN](https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/Tips_for_authoring_fast-loading_HTML_pages#Choose_your_user_agent_requirements_wisely)

[[↑] 回到顶部](#HTML)