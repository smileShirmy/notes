### angular2+ [hidden]

如果某个元素为display: flex 则会覆盖掉 [hidden]，可以使用*ngIf代替，或者全局设置

```css
[hidden] {
  display: none !important;
}
```

又或者

```css
<p [style.display]="hideElement?'none':'inherit'">
   I am using hidden.
</p>
```

### 更新包 npm update

### disablepictureinpicture

```
controlslist="nodownload" disablepictureinpicture
```

关闭 video 下载和画中画

