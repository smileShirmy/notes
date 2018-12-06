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