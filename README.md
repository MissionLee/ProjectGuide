# ProjectGuide

> 对我fork的源码，自己做的DEMO，自己开发的项目进行总结

## axios

> 通过自己开发的 promise-cache-controller

直接拉下来的源码，结合了另一个项目： promise-cache-controller 在axios中实现前端自动缓存数据

## promise-cache-controller

- 为上面扩展axios专门写的一个使用 promise语法进行前端缓存存取的工具类
- 会尝试使用 localstorage，降级使用内存

## DataStructureAndAlgorithms

一些简单的算法，数据结构的例子

## learn-axios 

在源码上写了非常多注释（基本涵盖了整个流程，很详细）
- 学到的内容
  - 基于promise的链式操作结构
  - 更多小技巧在注释里面总结了

## parameterConverter

设计用于探测参数，并对其根据配置进行自动抓换的工具类，实际用途不大，是我在学习设计模式的时候捣鼓出来的东西。
- 设计内容
  - 工厂模式：在configuration功能里，用 ConfigurationBuilder 创建 Configuration
  - 装饰模式：用各种提供统一功能的 Wrapper，来处理不同类型的输入数据
    - 在input包里面，有 InputWrapper 标准接口，并实现了 四种 Wrapper 来对四种不同输入数据进行“包装”

- 主要学到
  - 获取classloader，扫描本地文件，找到带有指定 注解的类，一次嗅探各种内置转换器并加载
  
## sockjs-client

通读源码，了解其降级机制于链接机制

> EventEmitter 通知设计模式是其中关键
> 深度解读运作原理 

## src[SpringMVCWebApplicationV0.2]

以SpringMVC为基础，配置的web项目，最初为了方便学习（SpringBoot封装完善，并不利于理解SpringMVC运行机制），所以使用了比较
原始的方式，需要配置 tomcat 才能够正常使用，配置流程在项目README里面

- 主要内容
  - 配置文件配置方式，协助学习tomcat响应请求的流程
  - 配置文件 + 配置类的配置方式，熟悉SpringMVC的配置（SpringBoot只需要配置文件，更加方便，单纯的SpringMVC也可以以配置类为主）
    - 包括配置 数据库，redis数据源
  - 设计了一套权限可配置认证体系，通过 HandlerInterceptor引入项目
  - 设计了一套 标准返回值处理体系（与对应的标准错误识别体系，标准错误代码体系），通过AOP引入项目
  - 常用工具类
    - 报错栈日志输出
    - Http请求参数汇总提取工具
    - 其他小工具
 
 ## demowebsocket
 
 SpringWebSocket + STOMP + SockJS + 自研的简单全局websocket链接复用工具类
 
 其中大多数内容为对 各种配置项目的配置测试，这部分能直接找到的“介绍，攻略”类的文章也不怎么全面，所以自己做了尝试，对其中一些内容也进行了解释
 
> Tips src/main 目录下有个 websockettest 那个是用 vue cli创建的测试用的项目 
>  yarn serve 运行测试项目
> websocket相关代码在 Home.vue 文件中，我在测试的时候，都是打开控制台，看Network里面的情况，所有没有像普通demo那样，弄个 按钮，对话框之类的