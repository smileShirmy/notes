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