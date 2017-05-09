# 为什么要选择使用React.js?
```
1.React 效率高，可以创建存放组件的虚拟DOM，　这一特点提供了高度灵活性和性能收益，　　
React能够提前计算出DOM中哪些内容需要更改，并对DOM树做出相应的更新，通过这种方式　　
React避免代价高昂的DOM操作，从而答复提升了工作效率
2.Javascript库，　　JSX是Javascript和Html的完美结合．可专门用于ReactJS,大　　
大简化了编写网站组件的流程．　　　
React的主要优势是合理的利用了本地API达到的夸平台效果
3.SEO友好，.以在服务器端运行React.js，虚拟DOM可以像常规的web页面一样返回给浏览器，不需要　　
任何特殊技巧。
4.注重用户界面，通过设备本地环境与React Native的Javascript交互，可以给用户提　　
供完美的响应式界面。虽然这一定程度上增加了应用的加载时间，但也保证了程序运行过程　　
中的流畅
5.简单，使用便捷,开发React项目，安装ReactJS的官方Chrome插件，它能使你的调试  
过程变得更加简单。安装完插件之后，你就可以像在元素面板中浏览一个常规DOM树一样  
直接查看虚拟DOM。
```
# React优０
```
React认为一个组件应该具有如下特征：

（1）可组合（Composeable）：一个组件易于和其它组件一起使用，或者嵌套在另一个组件内部。如果一个组件内部创建了另一个组件，那么说父组件拥有（own）它创建的子组件，通过这个特性，一个复杂的UI可以拆分成多个简单的UI组件；

（2）可重用（Reusable）：每个组件都是具有独立功能的，它可以被使用在多个UI场景；

（3）可维护（Maintainable）：每个小的组件仅仅包含自身的逻辑，更容易被理解和维护；
```
# React实现原理？
```
当用户点击组件，导致状态变化，this.setState 方法就修改状态值，每次修改以后，自动调用 this.render 方法，再次渲染组件。

这里值得注意的几点如下：

　　1、getInitialState函数必须有返回值，可以是NULL或者一个对象。

　　2、访问state的方法是this.state.属性名。

　　3、变量用{}包裹，不需要再加双引号。
```

# 说一下 React 组件更新原理。
```
React中的组件并不是真实的DOM节点, 而是存在于内存之中的一种数据结构,  
 叫做虚拟DOM(virtual DOM). 只是当它插入文档以后, 才会变成真实的DOM.  
 根据React的设计, 所有的DOM变动, 都先丰虚拟DOM上发生, 然后再将实际发  
 生变动的部分, 反映在真实DOM上, 这种算法叫做DOM diff, 这样可以大大提  
 高网页的性能表现.
```
# 说一下 React 的5个生命周期。
```
三个状态

Mounting: 已插入真实DOM
Updating: 正在被重新渲染
Unmounting: 已移出真实的DOM

五个声明周期处理函数

componentWillMount(): 在渲染前调用, 在客户端也在服务端.
componentDidMount(): 在第一次渲染后调用，只在客户端。之后组件已经生成　　
                      了对应的DOM结构，可以通过this.getDOMNode()来　　
                      进行访问。 如果你想和其他JavaScript框架一起使用，　　
                      可以在这个方法中调用setTimeout, setInterval或　　
                      者发送AJAX请求等操作(防止异部操作阻塞UI)。
componentWillUpdate(object nextProps, object nextState): 在组件接　　
                    收到一个新的prop时被调用。这个方法在初始化render时不　　
                    会被调用。
componentDidUpdate(object nextProps, object nextState): 返回一个布尔值。　　
                      在组件接收到新的props或者state时被调用。在初始化时或　　
                      者使用forceUpdate时不被调用。
componentWileUnmount(): 在组件从 DOM 中移除的时候立刻被调用。
```
# 说一下 props与state的区别。
```
state 与 props 的区别在于前者只存在于组件的内部. stats 可以用来确定一个元素的视图状态.
props：==一般用于父组件向子组件通信，在组件之间通信使用。
state：==一般用于组件内部的状态维护，更新组建内部的数据，状态，更新子组件的props等。
```
