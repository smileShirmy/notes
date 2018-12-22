### defineProperty() 和 defienProperties()

#####  defineProperty()

- 语法: Object.defineProperty(obj, prop, descriptor)
- obj: 需要被操作的目标对象
- prop: 目标对象需要定义或修改的属性的名称
- descriptor: 将被定义或修改的属性的描述符

##### Object.defineProperties()

- 语法: Object.getOwnPropertyDescriptor(obj, prop)
- obj: 需要查找的目标对象
- prop: 目标对象内属性名称

```javascript
Object.defineProperty(obj, 'key', {
    configurable : true,
    enumerable : true,
    get: function() {
        ...
    },
    set: function(newValue) {
        ...
    }
})
```


### 解构字符串

```javascript
[first, ...rest] = 'string'
console.log(first)  // "s"
cosnole.log(rest)   // ["t", "r", "i", "n", "g"]
```

### 移动端扩展点击区域

```javascript
// 扩展点击区域
@mixin extend-click() {
  position: relative;
  &:before {
    content: '';
    position: absolute;
    top: 1.5rem;
    left: 1.5rem;
    right: 1.5rem;
    bottom: 1.5rem;
  }
}
```

### scrollIntoView

- element.scrollIntoView() 参数默认为 true
- 参数为true时调用该函数，页面（或容器）发生滚动，使element的顶部与视图（容器）顶部对齐
- 参数为false时，使element的底部与视图（容器）底部对齐

```javascript
document.getElementById("view").scrollIntoView();

behavior: "auto"  | "instant" | "smooth",
block:    "start" | "end",
```

#### examples

如聊天窗口，当聊天气泡往下不断添加时，为了保证窗口在最下方，可使用scrollIntoView(false)

### replace

```javascript
let str = 'abc'
let value = str.replace(/a(.*?)c/g, '$1')	// b

value = str.replace(/a(.*?)c/g, ($1, string, offset) => {
	console.log($1)			// b
	console.log(string)		// abc
	console.log(offset)		// 0
})
```

### vue transition slide

```css
.slide-enter-active,
.slide-leave-active {
  transition: all 0.3s
}

.slide-enter,
.slide-leave-to {
  transform: translate3d(100%, 0, 0)
}
```

### reutrn cache[key] = key

### line-height: 1;

避免默认行高影响

### 文字两边对齐

```css
div {
	text-align: justify;
	display: inline-block;
	height: 40px;
	width: 70px;
	overflow: hidden;
	&::after {
		 content: "";
		 display: inline-block;
		 width: 100%;
	}
}
```

### vw vh

vw和vh是什么？

vw、vh、vmin、vmax是一种视窗单位，也是相对单位。它相对的不是父节点或者页面的根节点。而是由视窗（Viewport）大小来决定的，单位 1，代表类似于 1%。
视窗(Viewport)是你的浏览器实际显示内容的区域—，换句话说是你的不包括工具栏和按钮的网页浏览器。
具体描述如下：

- vw：视窗宽度的百分比（1vw 代表视窗的宽度为 1%）
- vh：视窗高度的百分比
- vmin：取当前Vw和Vh中较小的那一个值
- vmax：取当前Vw和Vh中较大的那一个值

vw、vh 与 % 百分比的区别

1. % 是相对于父元素的大小设定的比率，vw、vh 是视窗大小决定的。
2. vw、vh 优势在于能够直接获取高度，而用 % 在没有设置 body 高度的情况下，是无法正确获得可视区域的高度的，所以这是挺不错的优势。


[链接](https://juejin.im/post/5c18d8e2f265da61407ed721)

### CSS选择器排除最后两个

```css
&:not(:nth-last-child(-n + 2)) {
	...
  }
```

### 避免魔术数字 1 2 3 4

应当用常量来代替

```js
const XX_XX = 1
const XX_XXX = 2
``` 

### 相对父元素底部对齐

```css
.parent {
	.child {
		vertical-align: bottom;	
	}
}
```