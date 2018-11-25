### closure

- 闭包的作用域链包含着它自己的作用域，以及包含它的函数的作用域和全局作用域。
- 通常，函数的作用域及其所有变量都会在函数执行结束后被销毁。但是，在创建了一个闭包以后，这个函数的作用域就会一直保存到闭包不存在为止。

### 字符串补全(ES6)

**str.padStart(targetLength [, padString]) 在开头进行字符串补全**

**str.padEnd(targetLength [, padString]) 在结尾进行字符串补全**

```js
'zhangxinxu'.padStart(15, false);
// 结果是'falsezhangxinxu'
'zhangxinxu'.padStart(15, null);
// 结果是'nullnzhangxinxu'
'zhangxinxu'.padStart(15, []);
// 结果是'zhangxinxu'，因为[]转换成字符串是空字符串
'zhangxinxu'.padStart(15, {});
// 结果是'[objezhangxinxu'，只显示了'[object Object]'前5个字符

// 传统补全的方式
if (month < 10) {
    month = '0' + month;
}

// 使用 padStart
var month = String(new Date().getMonth() + 1).padStart(2, '0');    // 结果是'07'
```

[参考链接](https://www.zhangxinxu.com/wordpress/2018/07/js-padstart-padend/)

### BASE64 编码 解码

**atob 解码**

```js
// 语法为（浏览器中）：
var decodedData = window.atob(encodedData);

// 或者（浏览器或js Worker线程中）：
var decodedData = self.atob(encodedData);
```

**btoa 编码**

```js
// 语法为（浏览器中）：

var encodedData = window.btoa(stringToEncode);
// 或者（浏览器或js Worker线程中）：

var encodedData = self.btoa(stringToEncode);
```

[参考链接](https://www.zhangxinxu.com/wordpress/2018/08/js-base64-atob-btoa-encode-decode//)

### Vue中的data为什么是一个函数？

Object是引用数据类型,如果不用function 返回,每个组件的data 都是内存的同一个地址,一个数据改变了其他也改变了;

javascipt只有函数构成作用域(注意理解作用域,只有函数的{}构成作用域,对象的{}以及 if(){}都不构成作用域)，data是一个函数时，每个组件实例都有自己的作用域，每个实例相互独立,不会相互影响。

### inline-flex

inline-flex 把内联元素设置为 flex 弹性布局

使用flex布局后，float, clear, vertical-align属性失效

### transform和fixed

父元素有transform会直接导致fixed失效

https://www.zhangxinxu.com/wordpress/2015/05/css3-transform-affect/

### HTML 语义化

dl dt dd header main footer

### mouseenter cleartimeout querySelector

```javascript
// 通过 computed 切换 this.kind 来改变展示的数据
methos: {
    mouseleave() {
        this._timer = setTimeout(() => {
            this.kind = ''
        })
    },
    enter(e) {
        this.kind = e.target.querySelector('i').className
    },
    // 跨越DOM节点进入展开栏避免因mouseleave而隐藏
    sover() {
        clearTimeout(this._timer)
    },
    sout() {
        hhis.kind = ''
    }
}
```

### DOM + 语义化 + 强大的数据结构 = DOM结构最简化

### return () => { return ... }

避免返回的是一个常量

```javascript
get code(){
  return ()=>{
    return Math.random().toString(16).slice(2,6).toUpperCase()
  }
},
get expire(){
  return ()=>{
    return new Date().getTime()+60*60*1000
  }
}
```

### mangodb 数据库导入

```
// dbs 数据库
// test 数据结合
// pois.dat 数据源
mongoimport -d dbs -c test pois.dat
```

### split('')把每个字符作为数组元素

```javascript
'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('')
```

### 锚点 哈希跳转

```html
<a :href="'#city-" + item>{{item}}</a>
```

### 拼音库 js-pinyin

```javascript
'a'.charCodeAt(0)   // 97

let p
let c
let d = {}
city.forEach(item => {
    p = pyjs.getFullChars(item.name).toLocaleLowerCase().slice(0, 1)
    c = p.charCodeAt(0)
    // 小写的 a-z
    if ( c > 96 && c < 123) {
        if (!d[p]) {
            d[p] = []
        }
        d[p].push(item.name)
    }
})
for (let [k, v] of Object.entries(d)) {
    blocks.push({
        title: k.toUpperCase(),
        city: v
    })
}
// 按字母排序
blocks.sort((a, b) => a.title.charCodeAt(0) - b.title.charCodeAt(0))
```

### 组件化的含义

- 一定是**模板**+**数据结构**相辅相成
- 如果两方面都不擅长，说明组件化学习得不够深
- 用简洁的==数据结构==来帮助写出简单的模板及DOM结构
- 良好的组件设计，划分DOM结构，数据结构设计
- 前端有自己的数据结构，后端有自己的数据结构，前端不依赖于后端的数据结构
- 严格区分前端和后端你的数据
- 前端用==映射==的关系作为纽带，避免**过分依赖**
- 改JSON结构比改模板容易

### 综合技能

- 架构设计
- 前端组件设计
- 数据库设计
- 业务逻辑设计

### parseFloat()

```javascript
parseFloat('100%')  // 100
parseFloat('100.123123sadafd')  // 100.123123
```

### Math.max()

```javascript
Math.max.apply(null, [3, 1, 2])     // 3
Math.max(1, 2, 3, 4, 5)             // 5
Math.max(...[4, 2, 3, 1])           // 4
```

### Object.create

```javascript
var anotherObject = {
    a:2
}

// 创建一个关联到 anotherObject 的对象
var myObject = Object.create( anotherObject )
myObject.a   // 2
```

### git reflog

### Object.create(null) 和 {}

Object.create(null)没有继承任何方法，原型链没有上一层

```javascript
Object.create({}).toString      // function toString() { [native code] }
Object.create(null).toString    // undefined

Object.create(null)         // No properties
{}                          // __proto__ 相当于 new Object()
```

### 组件注册

- 通用的基础组件全局注册
- 业务组件局部注册

### getBoundingClientRect()

- 返回一个 DOMRect 对象
- 返回元素的大小及其相对于视口的位置。