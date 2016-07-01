# 写给自己，梳理一下我现在对前端知识结构的理解

今天想着做一件事情，给自己的收藏夹分类。结果做着做着，发现这个任务的工作量超乎我的想象。有一些文章，可能很难界定说，它是哪一类的；而且自己还没有特别去梳理自己对前端知识结构的理解，使得在分类的时候层级也有些模糊。所以在这里梳理一下自己理解中的知识结构。

这既是一篇总结，也是一篇指南，有些地方我自己亲身经历可能丰富一点，就说的多一些；有些地方自己没什么实践，就少说话，简单提一提，免得贻笑大方。

还有一点，这份指南中，个人色彩其实很重。有些学习方法上的建议，我都是从自己的经历出发的，但肯定不适合所有人。比如我喜欢浅阅读，看很多东西，需要用到的时候，心里有个大概，然后再深入研究，用到项目中。但我也遇到过一些喜欢深阅读的同学，他们看到一个东西就喜欢深入学习，举一反三。认识自己的特点并且选择适合自己的方法非常重要，就像小马过河的故事一样。

## JavaScript

就语言本身来说，JavaScript值得深究的地方不多。很多同学在最开始入行的时候（就像我），可能根本不懂就已经开始开发了。虽说在开发中踩坑，在踩坑中理解也未尝不可，不过我现在觉得，一开始先了解一些很常用的语法，还是很重要的。

我对前端的JavaScript学习，列出了这样的结构：

 - 语法
 - 框架与类库
 - 设计模式
 - 函数式
 - 底层
 - 发展

接下来就各个层面进行阐述：

### 语法

关于语法，JavaScript中值得注意的大点，其实也不是特别多，大概就以下几方面是比较常用的：

 - 变量提升
 - this 指向
 - 深复制和继承的写法
 - 闭包
 - 高阶函数
 - 异步与事件模型

关于语法，现有的资料其实很多。从我自己的学习经历来看，我是先简单过一遍《JavaScript高级程序设计》，有一个大概的理解，另外准备一本《JavaScript权威指南》当字典（高程其实也是字典）。建议深入阅读[《You Don't Know JS》](https://github.com/getify/You-Dont-Know-JS)这一系列，写的真心非常好。

其他资料也推荐一些供大家选择：

 - [JavaScript秘密花园](http://bonsaiden.github.io/JavaScript-Garden/zh/)
 - [Mozilla 开发者网络](https://developer.mozilla.org/)

### 框架与类库

其实很多时候，能听到将jQuery称为框架的这种声音，我觉得是不妥的。目前我觉得，常用的第三方包大概两种，框架（framework）和库（library）。我界定两者的标准是：框架会影响到你项目的目录结构、代码结构以及编程模型这些设计相关的东西，而库则仅仅是提供了某些或某类操作的简洁封装方便调用。框架中包含的概念，一般要比库复杂的多，所以我觉得jQuery是一个库，提供了关于DOM操作，Ajax请求等一系列常用操作的简洁封装，而算不上框架。

就我所知，现在比较常见的框架如下：

 - React
 - Angular 2
 - Angular 1
 - Ember
 - Polymer
 - Vue
 - Riot

有人还做了这样一张表格，将这些框架进行了对比：[Front-end Hyperpolyglot](http://jeffcarp.github.io/frontend-hyperpolyglot/)

其实还有rxjs / cycle.js这个纯粹的函数式的框架活跃着，ng2使用了rxjs，React也从中借鉴了思想（包括在redux中用rxjs处理异步Action），但纯粹用这一套的项目，应该还是demo多吧。

我对于框架学习的态度是：将一个真正用到项目中，了解一下其他框架的特点和主要思想（当然时间足够且不怕忘的话，多来几个也没问题，还是那句话，根据自己特点来）。其实哪怕框架过时了，思想也还是有价值的。之前和[@RizzleCi](https://github.com/RizzleCi)聊的时候，她说觉得现在就很像jQuery统治世界之前的样子。现在来看，最终谁会胜出还是个未知数。

然而对于很多同学来说，可能很难去在项目中学习一个框架：自学只能敲demo，项目不熟不敢用。确实，demo的复杂度不足以让你从工程的层次去学习框架，而这一点我的建议就是，借用公共的API进行开发。我推荐使用GitHub和豆瓣（并不是广告），其他文档全面稳定且复杂度足够的API也没有问题。我认为只要你开发了一个足够复杂的前端项目，就能切身体会到框架所带来的优缺点。（其实只要解除跨域限制，哪的API都可以用，方法就是使用代理软件，后面讲开发与调试的时候会具体说）

上面说的这些框架，更准确的来说，其实是专注于将表现和数据分离的框架。其实还有很多框架不在这一类，如针对游戏开发的Egret。（游戏这个领域我没有接触过，点到为止）

说到库的话，我觉得大概有两类：一类相对来说通用一些，如jQuery、lodash；另一类相对专用，如针对数据可视化的D3、Highcharts，针对3D图形的three.js，甚至比较简单的如针对时间处理的moment等等。整体来说，库的上手程度不高，比如jQuery，理解清楚被jQuery的$符包裹的对象和普通DOM的区别及其相互转化，剩下的应该就只有查文档了。

### 设计模式

对设计模式的使用，应该是一种经验的体现。由于个人经验缺乏，我现在对设计模式用的很少，仅仅简单实践过像策略模式、装饰者模式这些。我认为设计模式应该是要用心去学习的一个点，也是提升能力的一个有效途径。

相关资料：

 - 《JavaScript设计模式与开发实践》
 - [常用的Javascript设计模式](http://web.jobbole.com/29454/)

### 函数式

前端的函数式编程，应该是在近年来火起来的。其实在高级程序设计上，就对JavaScript的函数式编程有所涉及。函数式编程的起源要从λ演算说起，有兴趣可以查阅相关资料。就我目前的感觉来说，在JavaScript中应用函数式编程更像是一种高级技巧，这种技巧一般都会涉及到闭包和高阶函数，反正我觉得，真心好用。

举一个简单的例子：写一个`before`函数（`before(count, function)`），返回一个函数，调用不超过`count`次。 当`count`已经达到时，最后一个函数调用的结果将被记住并返回。

比如，我传入这样一个函数：

```js
function log() {
  console.log.apply(console, arguments)
  return arguments[0]
}
```

用`before`函数获得只能执行3次的log：

```js
var log3 = before(3, log)

log3(1)   // 1
log3(2)   // 2
log3(3)   // 3
log3(4)   // 什么都没有log
```

想一想，你会怎么实现这个`before`函数。（[答案传送门](https://github.com/jashkenas/underscore/blob/master/underscore.js#L921)）

还有一些非常常用的函数节流技巧（`throttle`、`debounce`）、封装一些原生函数（如`fetch`），都会用到这相关的技巧。在ES7中，提供了Decorators相关的语法，让你更方便的使用这些技巧。（这其实就是JavaScript中的装饰者模式实践）

许多框架在设计上借鉴了函数式的技巧，比较明显的就是Redux，包括在Redux的源码中，也遍布各种函数式的思维。rxjs更是将这种思维贯彻到了一个极致。我觉得将来rxjs包括cycle.js肯定会在框架中占据一席之地，目前来说，至少RxJava发展的还是挺好的。

推荐：

 - [JS函数式编程指南](https://www.gitbook.com/book/llh911001/mostly-adequate-guide-chinese/details)

### 底层

JavaScript能有今天的发展跟V8是脱不了关系的。很多讲解JavaScript优化的文章，都会提到V8相关的实现。

不过我觉得，对于V8这一层面的东西，离前端还是有点远了。目前我在浏览器开发，没遇到过什么性能上的大问题，学习V8源码，也不算是核心痛点。推荐几篇相关文章：

 - [A tour of V8](http://jayconrod.com/tags/v8)
 - [V8常见去优化原因一览](http://alinode.aliyun.com/blog/25)

### 发展

其实很想吐槽一下，现在的JS，一年一个版本，太可怕了。

当然，确实提供很多非常好用的语法（糖），比如class、解构、箭头函数这些，我是挺喜欢用的。

另外一支很有势头的发展就是TypeScript，给JavaScript加入了强类型，使其更易于开发大型项目（接口的规范与更好的错误提示）。AngularJS 2已经全面拥抱TypeScript了，蚂蚁金服的Ant-Design也已经切换到了TypeScript，可见其提供的特性还是很有吸引力的。在微软推出了VS Code之后，TypeScript也有了官方的编辑器，值得一试。

在使用这些新特性的时候，一般都会用到类似babel这种转换工具。关于这类工具的介绍，会在下面讲开发与调试的时候提到。

## HTML & CSS

很多前端同学应该都是从这个地方入的坑吧。关于HTML和CSS的技巧，我觉得现在自己已经在某种程度上生疏了，毕竟很久没有自己写过了。

其实这个领域曾经带给我很多乐趣，黑科技在某种程度上讲要比JavaScript多很多，而且也是和浏览器兼容的斗争最紧张的地方。

学习CSS的话，推荐下面这些材料：

 - 《精通CSS（第2版）》
 - 张鑫旭的博客：[http://www.zhangxinxu.com/](http://www.zhangxinxu.com/)
 - w3cplus[http://www.w3cplus.com/](http://www.w3cplus.com/)
 - 前端乱炖[http://www.html-js.com/](http://www.html-js.com/)

## 开发与调试

准备好了基础知识，让我们简单了解一下开发与调试相关的东西。在这一部分中，工具发挥着很大的作用。

我将按照如下顺序阐述这一部分：

 - 规范
 - 构建
 - 调试
 - 协同
 - 测试
 - 性能

### 规范

没有规矩不成方圆，写代码的时候团队肯定要有一套规范。也有许多团队将他们的规范拿了出来，比如：

 - [alloyteam代码规范](http://alloyteam.github.io/CodeGuide/)
 - [airbnb代码规范](https://github.com/airbnb/javascript)

其他团队的规范未必适合自己，只要团队成员达成共识，就是好的规范。

在代码commit之前进行规范的检测是一个比较合适的时机，npm提供了一个叫做`pre-commit`的包，结合`eslint-config-airbnb`，可以搭建一套用于质量保证的东西出来。

相关资料：

 - [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)
 - [pre-commit](https://www.npmjs.com/package/pre-commit)

### 构建

构建一般是使用webpack来进行，依靠各种强大的loader，可以完成一系列功能。

相关资料：

 - [React Webpack 小书](http://fakefish.github.io/react-webpack-cookbook/)
 - [Webpack傻瓜指南（三）和React配合开发](https://zhuanlan.zhihu.com/p/2052248)
 - [webpack使用优化](http://www.alloyteam.com/2016/01/webpack-use-optimization/)
 - [如何 10 倍提高你的 Webpack 构建效率](http://eternalsky.me/ru-he-10-bei-ti-gao-ni-de-webpack-gou-jian-xiao-lu/)

如果上面看着迷糊，希望找一个配置好的东西直接拿来用，我推荐使用`atool-build`，无论你是ES6、React还是TypeScript，都已经配置好了。可以先用着，明白怎么回事以后，再开始搞自己的`webpack.config`。

 - [Ant-Tool](http://ant-tool.github.io/index.html)

### 调试

我最常用的工具应该就是Chrome Dev Tools了：

 - [Chrome开发者工具系列](http://www.cnblogs.com/constantince/category/712675.html)
 - [chrome 控制台使用指南](http://frontenddev.org/column/chrome-development-tools-using-guide/)
 - [Chrome开发者工具之JavaScript内存分析](http://www.open-open.com/lib/view/open1421734578984.html)
 - [一探前端开发中的JS调试技巧](http://seejs.me/2016/03/27/jsdebugger/)

另外就是前面提到过的代理工具，Chrome插件Proxy SwitchyOmega配合fiddler / charles，进行线上调试。如果代理的自定义需求比较高，工具的正则满足不了，可以尝试自己写一个nodejs程序，用`http-proxy`这个包来将资源代理到本地。

 - [如何使用Fiddler调试线上JS代码](http://www.cnblogs.com/RockLi/p/3511132.html)
 - [在线调试利器Fiddler AutoResponse](http://www.cnblogs.com/peak-weng/archive/2012/01/19/2325855.html)

### 协同

推荐使用git，毕竟GitHub对于开发者已经如同简历、名片一般。

 - [廖雪峰的Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
 - [基于git的源代码管理模型——git flow](http://www.ituring.com.cn/article/56870)
 - [我的提交信息规范](http://yanhaijing.com/git/2016/02/17/my-commit-message/)

### 测试




## 工程问题

### 性能

前端性能问题，很难在写的时候就全都避免，一般都是在开发完成的测试阶段遇到问题后逐步排查的，总会多少经历一个迭代的过程。

相关资料推荐：

 - [JavaScript 性能优化杀手](http://dev.zm1v1.com/2015/08/19/javascript-optimization-killers/)
 - [编写高性能JavaScript](http://www.alloyteam.com/2012/11/performance-writing-efficient-javascript/)
 - [渲染性能](https://github.com/sundway/blog/issues/2)
 - [了解 JavaScript 应用程序中的内存泄漏](http://www.ibm.com/developerworks/cn/web/wa-jsmemory/)
 - [js内存泄漏常见的四种情况](https://segmentfault.com/a/1190000004896090)
 - [搞定JavaScript内存泄漏](https://boke.io/gao-ding-nei-cun-xie-lou/)

### 安全


 - [事件还原：一封QQ恶意邮件，导致Apple ID密码丢失](http://www.freebuf.com/vuls/85053.html)
 - [一个 JSON 跨域获得数据漏洞的分析](http://ju.outofmemory.cn/entry/62159)
 - []()

### 监控

## 业务场景

### PC端

### 移动端

### 细分场景

## 面试

### 试题的积累

### 项目的积累

### 思考的积累

## 前瞻

## 其他

### 提问

### 数据结构与算法

### HTTP

### 后端和数据库

### Linux
