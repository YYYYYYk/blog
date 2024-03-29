# 基础

## 二维数组
``` js
// 二维数组的创建
let arr = new Array(10); //表格有10行
for(let i = 0;i < arr.length; i++){
  arr[i] = new Array(10).fill(0); //每行有10列
}
arr[0][0] = 1
```
[创建二维数组](https://juejin.cn/post/6968645442691137572)
[![pSvHRMD.md.png](https://s1.ax1x.com/2023/02/23/pSvHRMD.md.png)](https://imgse.com/i/pSvHRMD)

## js数据类型
- 基本数据类型：`String`、`Number`、`Bool`、`Null`、`Undefined`、`bigInt`、`symbol` 
- 引用数据类型：`Object`、`array`、`function`
::: tip
- 含义不同: 基本数据类型存放是个值，而引用数据类型存放的是个地址。 基本数据类型的值是存储在栈中的，而引用类型栈中存放的是地址，具体内容存放在堆中。
- 作为形参调用时，修改形参值， 基本数据类型不影响原数据。而引用值传递，修改形参值，会影响原数据。
:::
### 判断数据类型
``` js
export const isDate = (val: unknown): val is Date => val instanceof Date
export const isFunction = (val: unknown): val is Function => typeof val === 'function'
export const isString = (val: unknown): val is string => typeof val === 'string'
export const isSymbol = (val: unknown): val is symbol => typeof val === 'symbol'
// typeof null 其实还是 'object',需区分开来
export const isObject = (val: unknown): val is Record<any, any> => val !== null && typeof val === 'object'  
```

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


## Object.defineProperty
``` js
Object.defineProperty(object1, 'property1', {
  value: 42,
  configurable: true, // 是否可被删除
  enumerable: false,  // for in 中是否被枚举
  writable: false // 是否可修改值
});
```

## 文章
- [事件的监听与移除](https://blog.csdn.net/qq_29606781/article/details/67650869)



