# 基础
## 1.MVVM
  M: 数据模型 - JS块中data数据

  V: 视图 - 前端html代码

  VM: 调度者 - JS块，相当于vue的实例, 监听数据模型改变和视图上的行为，简单点就是连接数据和视图

## 2.SPA
  单页web应用(single page web application)
  1. 只有1个完整页面（1个index.html），多个组件
  2. 点击页面中的链接不会刷新页面，只会做局部更新
  3. 数据都通过ajax异步展示到前端

## 3.h函数

## 4.组件传值
- provider & inject
``` js
provide() {
	return {
		commonData: this.vipCommon,  // 值依赖于data所定义的值
		getNewstValue: () => this.vipCommon // 能获取响应式的值
		updateCommonData: this.updateCommonData. // methods
	}
},
inject:['commonData', 'updateCommonData'],
// 相应式取值
Computed: {
    newCommonData() {
        return this.getNewstValue()
	}
}
```