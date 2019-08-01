## Git commit message规范

## 1. 为什么要有git commit message规范

- 统一git提交描述信息
- 发生问题需要代码回滚时快速找到对应的commit
- 快速生成语义化的changelog

### 2. 什么样的git commit message比较好

- 简明扼要
- 准确表达所提交代码的信息

### 3. 如何写出规范的git commit message

当前业界应用比较广泛的是[Angular Git Commit Guidelines](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines)

具体格式为：

> ```
> <type>(<scope>): <subject>
> <BLANK LINE>
> <body>
> <BLANK LINE>
> <footer>
> ```
>
> ### **4. 通过第三方工具生成和约束git commit message**
>
> 我们也可以引入诸如[commitizen](https://github.com/commitizen/cz-cli)配套git hooks来自动化生成和约束我们的提交描述信息，中心思想就是commitizen会通过我们指定的[adapter](https://github.com/commitizen/cz-cli#adapters)以命令行的形式帮助我们生成描述信息。
>
> 但工具主要用于开源软件的迭代，对于平时的业务开发、快速原型开发的必要性不大，有兴趣的可以自己查阅。
>
> 不引入工具就更依赖大家的自觉性，俗话说得好：约定大于配置~
>
> 
>
> 例如：修复订单列表页文案错误；重构图片上传组件
>
> **subject：**commit的具体描述，要求简明扼要，建议“动词” + “名词”，多条独立信息可以使用分号分割，结尾不写英文或中文句号。
>
> **scope**：commit影响的范围，比如：route、component、utils、build等等，如影响多个范围可用星号省略，比如：范围1，范围2，可以用 type(*范围1)表示
>
> 
>
> 特殊：如果当前提交是为了revert之前的commit，则格式为：revert + 冒号 + 被还原commit的message的完整header eg: revert:feat(route):增加路由
>
> - **feat： 新特性**
> - **fix： bug修复**
> - **docs： 仅仅更改了项目文档**
> - **style： 没有影响代码逻辑的修改（比如换行冒号等代码格式化所产生的修改，注意并不是css修改， css修改属于代码逻辑修改）**
> - **refactor：重构代码（也可以被描述为既没有修复bug也没有增加feature的修改）**
> - **pref： 为提升性能所进行的修改**
> - **test： 添加之前缺失的测试或更新现有的测试代码**
> - **chore： 对项目构建或辅助工具、引入库(包)的修改**
> - **merge： 分支合并**
>
> **type**: 必须是下面类型中的一种（若一次提交中预计包含多种type：个人建议分多次提交写不同的type；也可以选择较主要的type，一起提交）
>
> 
>
> **header**中包含type、scope和subject，总字符不宜超过100个：
>
> 在业务项目开发中一般只写header即可，body一般用于开源项目生成changelog等。本文只介绍header的具体写法，其余暂不介绍，有兴趣可点击链接查阅
>
> 其中的第一行header是强制性的，header中的scope是可选，其余必填