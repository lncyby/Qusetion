# Node.js 基础知识
1. 为什么要用node?
```
总结起来node有以下几个特点:简单强大，轻量可扩展．简单体现在node使用的是javascript,json来进行编码，  
人人都会；强大体现在非阻塞IO,可以适应分块传输数据，较慢的网络环境，尤其擅长高并发访问；轻量体现在node  
本身既是代码，又是服务器，前后端使用统一语言;可扩展体现在可以轻松应对多实例，多服务器架构，同时有海量  
的第三方应用组件．
```
##### 正如JavaScript为客户端而生,Node.js 为网络而生。Node.js 能做的远不止开发一个网站那么简单,使用 Node.js,你可以轻松地开发:
```
1. 具有复杂逻辑的网站;
2. 基于社交网络的大规模 Web 应用;
3. Web Socket 服务器;
4. TCP/UDP 套接字应用程序;
5. 命令行工具;
6. 交互式终端程序;
7. 带有图形用户界面的本地应用程序;
8. 单元测试工具;
9. 客户端 JavaScript 编译器。
```
### Node.js优点：
```
1. 采用事件驱动、异步编程，为网络服务而设计。其实Javascript的匿名函数和闭包特性非常适合事件驱动、异步编程。  
而且JavaScript也简单易学，很多前端设计人员可以很快上手做后端设计。
2. Node.js非阻塞模式的IO处理给Node.js带来在相对低系统资源耗用下的高性能与出众的负载能力，非常适合用作依  
赖其它IO资源的中间层服务。
3. Node.js轻量高效，可以认为是数据密集型分布式部署环境下的实时应用系统的完美解决方案。  
Node非常适合如下情况：在响应客户端之前，您预计可能有很高的流量，但所需的服务器端逻辑和处理不一定很多。
```
### Node.js缺点：
```
可靠性低
单进程，单线程，只支持单核CPU，不能充分的利用多核CPU服务器。一旦这个进程崩掉，那么整个web服务就崩掉了。
不过以上缺点可以可以通过代码的健壮性来弥补。

目前Node.js的网络服务器有以下几种支持多进程的方式：

开启多个进程，每个进程绑定不同的端口，用反向代理服务器如 Nginx 做负载均衡，好处是我们可以借助强大的 Nginx   
做一些过滤检查之类的操作，同时能够实现比较好的均衡策略，但坏处也是显而易见——我们引入了一个间接层。
多进程绑定在同一个端口侦听。在Node.js中，提供了进程间发送“文件句柄” 的功能，这个功能实在是太有用了  
（貌似是yahoo 的工程师提交的一个patch） ，不明真相的群众可以看这里： Unix socket magic
一个进程负责监听、接收连接，然后把接收到的连接平均发送到子进程中去处理。在Node.js v0.5.10+ 中，  
内置了cluster 库，官方宣称直接支持多进程运行方式。Node.js 官方为了让API 接口傻瓜化，用了一些比较tricky的方法，  
代码也比较绕。这种多进程的方式，不可避免的要牵涉到进程通信、进程管理之类的东西。
此外，有两个Node.js的module：multi-node 和 cluster ，采用的策略和以上介绍的类似，但使用这些module往往有一些缺点：
1. 更新不及时
2. 复杂庞大，往往绑定了很多其他的功能，用户往往被绑架
3. 遇到问题难以解决
```

2. node的构架是什么样子的?
```
主要分为三层，应用app >> V8及node内置架构 >> 操作系统. V8是node运行的环境，可以理解为node虚拟机．  
node内置架构又可分为三层: 核心模块(javascript实现) >> c++绑定 >> libuv + CAes + http.
```
3. node有哪些核心模块?
```
 EventEmitter, Stream, FS, Net和全局对象
```
4. node有哪些全局对象?
```
process, console, Buffer和exports
```
5. process有哪些常用方法?
```
process.stdin, process.stdout, process.stderr, process.on, process.env,   
process.argv, process.arch, process.platform, process.exit
```
6. console有哪些常用方法?
```
console.log/console.info, console.error/console.warning,   
console.time/console.timeEnd, console.trace, console.table
```
7. node有哪些定时功能?
```
 setTimeout/clearTimeout, setInterval/clearInterval, setImmediate/clearImmediate, process.nextTick
```

# Node.js 事件

1. Promise 中 .then 的第二参数与 .catch 有什么区别?
1. Eventemitter 的 emit 是同步还是异步?
1. 如何判断接口是否异步? 是否只要有回调函数就是异步?
1. nextTick, setTimeout 以及 setImmediate 三者有什么区别?
1. 如何实现一个 sleep 函数?
1. 如何实现一个异步的 reduce? (注:不是异步完了之后同步 reduce)
1. node中的事件循环是什么样子的?
1. 什么是EventEmitter?
1. 如何实现一个EventEmitter?
1. EventEmitter有哪些典型应用?
1. 怎么捕获EventEmitter的错误事件?
1. EventEmitter中的newListenser事件有什么用处?
