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