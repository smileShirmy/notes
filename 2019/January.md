### window.postMessage

示例

```typescript
(document.getElementById("circuit_iframe") as HTMLIFrameElement).contentWindow.postMessage(data, "*");
```

- window.postMessage() 方法可以安全地实现跨源通信
- 向目标窗口发送MessageEvent消息
- ```otherWindow.postMessage(message, targetOrigin, [transfer]);```
- message: 将要发送到其他 window的数据。它将会被结构化克隆算法序列化。这意味着你可以不受什么限制的将数据对象安全的传送给目标窗口而无需自己序列化。
- targetOrigin: 如果你明确的知道消息应该发送到哪个窗口，那么请始终提供一个有确切值的targetOrigin，而不是*。不提供确切的目标将导致数据泄露到任何对数据感兴趣的恶意站点]。

### function是语法糖 相当于 new Function()

```javascript
function Foo() {}
// 这个函数是 Function 的实例对象
// function 就是一个语法糖
// 内部调用了 new Function(...)
let a = { b: 1 }
// 这个字面量内部也是使用了 new Object()
```

### 原型链

- ```Object``` 是所有对象的爸爸，所有对象都可以通过 ```__proto__``` 找到它
- ```Function``` 是所有函数的爸爸，所有函数都可以通过 ```__proto__``` 找到它
- ```Function.prototype``` 和 ```Object.prototype``` 是两个特殊的对象，他们由引擎来创建
- 除了以上两个特殊对象，其他对象都是通过构造器 ```new``` 出来的
- 函数的 ```prototype``` 是一个对象，也就是原型
- 对象的 ```__proto__``` 指向原型， ```__proto__``` 将对象和原型连接起来组成了原型链

[](https://github.com/KieSun/Blog/issues/2)

### 立即执行函数 上下文

```javascript
var foo = 1
(function foo() {
    foo = 10
    console.log(foo)
}()) // -> ƒ foo() { foo = 10 ; console.log(foo) }
```

### 放弃解决冲突 git merge --abort

放弃此次的merge 

### git stash -u

单单是git stash 不会把未跟踪的文件也保存起来，因此要加上`-u`，即 ```--include-untracked``` 的简写

### 表单避免多次点击导致多次重复提交

### checkbox 样式

```html
<label class="my_protocol">
      <input class="input_agreement_protocol" type="checkbox" />
      <span></span>
</label>
```

```css
/*隐藏掉我们模型的checkbox*/
.my_protocol .input_agreement_protocol {
    appearance: none;
    -webkit-appearance: none;
    outline: none;
    display: none;
}

/*未选中时*/        
.my_protocol .input_agreement_protocol+span {
    width: 16px;
    height: 16px;
    background-color: red;
    display: inline-block;
    background: url(../../Images/TalentsRegister/icon_checkbox.png) no-repeat;
    background-position-x: 0px;
    background-position-y: -25px;
    position: relative;
    top: 3px;
}
/*选中checkbox时,修改背景图片的位置*/            
.my_protocol .input_agreement_protocol:checked+span {
    background-position: 0 0px
}
```

```less
  /*隐藏掉我们模型的checkbox*/
  .resource-input-label{
    .resource-input {
      appearance: none;
      -webkit-appearance: none;
      outline: none;
      display: none;
    }
    /*未选中时*/        
    .resource-input + span {
      width: 13px;
      height: 13px;
      background: url('../images/checkbox@uncheck.png') no-repeat;
      display: inline-block;
      position: relative;
    }
    /*选中checkbox时,修改背景图片的位置*/            
    .resource-input:checked + span {
      background: url('../images/checkbox@checked.png') no-repeat;
    }
  }
```

### git stash pop 和 git stash apply

- git stash pop 会清空git stash 暂存
- git stash apply 不会清空git stash 暂存

### git 工作流

- 功能分支前缀：feature/
- 发布版本分支前缀：release/
- 修复补丁分支前缀：hotfix/

### 监听window.open的页面关闭

```js
win = window.open(index.html)

interval(() => {
	if (win.closed === true){ ... }
}, 1000)
```

### 用雪碧图提前加载小图标，避免图标为空，优化体验

### white-space: pre-line; 保留换行

white-space 还有其他属性

### 'Content-Type': 'application/x-www-form-urlencoded'

### query是url参数 payload 是body参数

### clearfix

```css
.clearfix:after {
    content: "";
    display: block;
    height: 0;
    clear: both;
    visibility: hidden;
    overflow: hidden;
}
```

### getBoundingClientRect()

- Element.getBoundingClientRect()方法返回元素的大小及其相对于视口的位置。

### offsetLeft 和 style.left

- offsetLeft 获取的是相对于父对象的左边距
- left 获取或设置相对于 具有定位属性(position定义为relative)的父对象 的左边距
- 区别：
1. style.left 返回的是字符串，如28px，offsetLeft返回的是数值28，如果需要对取得的值进行计算，用offsetLeft比较方便。
2. style.left是读写的，offsetLeft是只读的，所以要改变div的位置，只能修改style.left。
3. style.left的值需要事先定义，否则取到的值为空。而且必须要定义在html里，我做过试验，如果定义在
css里，style.left的值仍然 为空，这就是我刚开始碰到的问题，总是取不到style.left的值。

offsetLeft则仍然能够取到，无需事先定义div的位置。

### Vue .native

- .native - 监听组件根元素的原生事件。 
- 区分自定义事件和
- 如果不写 .native 修饰符，那 @click 就是自定义事件 click，而非原生事件 click

如：

```html
<i-button @click.native="handleClick"></i-button>
```