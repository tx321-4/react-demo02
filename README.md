# 阮一峰的React 入门实例教程 练习

> react.dev 版本16.7

# 一 ReactDOM.render()   

ReactDOM.render 是 React 的最基本方法，用于将模板转为HTML语言，并插入指定的DOM节点中  
&nbsp;  
# 二  JSX 语法 
介绍：HTML语言直接写在Javascript语言之中，不加任何引号，这就是JSX语法,它是HTML与JavaScript的混写

* 遇到HTML标签（以 `<` 开头）,HTML解析
* 遇到代码块（以`{` 开头）,JavaScript 解析
* JSX 允许直接在模板插入JavaScript 变量，如果变量是一个数组，则会展开这个数组的所有成员  
&nbsp;  
# 三 组件 
React 允许将代码封装成组件,像插入HTML标签一样，插入节点中，
* React.createClass方法用于生成一个组件类
* 所有组件必须有自己的render方法，用于输出组件
* 组件类的第一个字母必须是大写，否则会报错，
* 组件类只能包含一个顶层标签
* 组件的用法与HTML标签完成一致，可以任意加入属性，
* 组件的属性可以在组件类的`this.props` 对象中获取,比如`name`属性可以通过`this.props.name`读取
* 添加组件属性，要注意，`class`属性需要改为`className`，`for`属性需要改为`htmlFor`，这是因为`class`和`for`是JavaScript 的保留字

> funtion 组件与 class 组件有什么区别

&nbsp;  
# 四 this.props.children

> 它表示组件的所有子节点
* 可以通过`this.props.children` 读取子节点
* React提供一个工具方法 `React.Children`来处理`this.props.children`

&nbsp;  
# 五 PropTypes
> 组件类的`PropTypes`属性,就是用来 验证组件实例的属性是否符合要求

&nbsp;  
# 六 获取真实的DOM节点

* 组件不是真实的节点，而是存在内存之中的一种数据结构，叫做虚拟DOM, 只有当插入文档以后，才会变成真实的DOM。
* 根据React的设计，所有的DOM变动，都现在虚拟DOM上发生，然后再将实际发生变动的部分，反映在真实的DOM上，这种算法叫做`DOM diff`, 作用是可以提高网页的性能表现
* 获取真实的DOM节点，我们需要用到`ref`属性

&nbsp;  
# 七 this.state
* React 把组件看成是一个状态机，yi开始有一个初始状态，然后用户互动，导致状态变化，从而触发重新渲染UI
* 可以通过`this.state` 读取对象，状态变化，`this.setState` 方法 就修改状态值，每次修改以后，自动调用`this.render`方法，重新渲染组件
* `this.props`和`this.state`都是用来描述组件的特性,区别在于，`this.state`是会随用户互动而产生变化的特性,`this.props` 表示一旦定义，就不再改变的特性
