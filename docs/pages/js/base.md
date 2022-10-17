# 基础

## js数据类型
- 基本数据类型：`String`、`Number`、`Bool`、`Null`、`Undefined`、`bigInt`、`symbol` 
- 引用数据类型：`Object`、`array`、`function`
::: tip
- 含义不同: 基本数据类型存放是个值，而引用数据类型存放的是个地址。 基本数据类型的值是存储在栈中的，而引用类型栈中存放的是地址，具体内容存放在堆中。
- 作为形参调用时，修改形参值， 基本数据类型不影响原数据。而引用值传递，修改形参值，会影响原数据。
:::

## 作用域链
由于**函数嵌套**的原因会有个作用域的层级系，当函数执行时，会从当前作用域开始搜索，若没有则会向上层作用域搜索，**直到全局函数**，这就是作用域链。
::: tip
- 全局函数不能查看局部函数的作用域的变量，但局部函数作用域可以查看上层函数 细节，直到全局细节。
- 闭包的原理就涉及到作用域链的知识。
:::

## 纯函数、高阶函数、函数柯里化
 **纯函数**: 一个函数的返回结果只依赖其参数，并且执行过程中没有副作用

 **高阶函数**: 符合下面2者之一即可
  1. 若一个函数，接收的参数是个函数，那么可称之为高阶函数
  2. 若一个函数，返回值是个函数。
   
::: tip
常见的高阶函数： Promise、settimeout、arr.map
:::

**[函数柯里化](https://blog.csdn.net/m0_52409770/article/details/123359123?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-123359123-blog-123234634.pc_relevant_multi_platform_whitelistv3&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-123359123-blog-123234634.pc_relevant_multi_platform_whitelistv3&utm_relevant_index=1)**: 通过函数调用继续返回函数的方式，实现多次接受参数最后统一处理的编码形式。






## 文章
- [事件的监听与移除](https://blog.csdn.net/qq_29606781/article/details/67650869)

## tips
### DOM的类操作
1. 添加
```js
// 新类名会覆盖原有的类名
DOM.setAttribute('class', '类名1')
// 不会覆盖已有的类名
DOM.classList.add('类名1', '类名2')
// 添加内联样式
DOM.style.cssText="height: 200px;"
DOM.setAttribute('style', "height: 200px;")
```
2. 删除
```js
DOM.classList.remove('类名1', '类名2')
```
3. 是否包含某类
```js
DOM.classList.contains('类名')  // return true or false
```
### Math.random生成随机数
> Math.floor向下取整
- 比如要生成范围0-19的整数，`Math.floor(Math.random()*20)`
- 比如要生成范围10-20的整数，`Math.floor(Math.random()*11+10)`
### 匿名函数
```js
(() => {})()
```
### 辨析event.target和event.currentTarget
2者在没有冒泡的情况下，是一样的值。

在有冒泡的事件中，如<u>给父元素绑定点击事件，然后点击子元素</u>。`event.target`是实际触发的元素，`event.currentTarget`是事件绑定的元素，就是父元素

### 原生点击事件的触发3种方式
1. 添加onclick事件
2. 获取dom，dom.addEventListener('click', () => {   })
3. 获取dom，dom.onclick = () => {}

### 元素移动
- `append`，`appendChild`移动成功后会删除旧节点
- `cloneNode`复制节点，不会删除旧节点
  
