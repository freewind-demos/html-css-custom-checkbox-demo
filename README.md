Html Css Custom Checkbox Demo
=============================

Checkbox的styling不太容易，有几个地方需要注意：

1. 默认的复选框的样式是由浏览器提供的，基本上不能为它设置样式。
   比如框的大小没法用`px`指定，使用`transform: scale(2)`或者`zoom: 2`来放大，要么效果不好有毛边，要么有的浏览器不支持。
   
2. 如果想对复选框进行设置，需要先隐藏浏览器自带的效果，使用`appearance:none`。
   - 但是`appearance`现在浏览器不认，必须在前面加前缀，比如`-webkit-appearance/-moz-appearance`等
   - `appearance:none`之后，就可以使用通常的style来修饰，比如width/height/border等

3. 需要自定义的勾选效果，可以使用background-image

4. label与input结合之后，会遇到复选框与文字对齐的问题（文字通常会偏下），这时需要比较复杂的方式（比如`position/display/vertical-align/padding`等结合）才能调整好。

5. 对checkbox使用`all: initial`来重置其样式后，会发现复选框不显示，原因是`appearance`被重置后，会丢失原始的`checkbox`样式。所以需要手动指定：
    ```
    input[type=checkbox] {
      all: initial;
      -webkit-appearance: checkbox;
      -moz-appearance: checkbox;
      appearance: checkbox;
    }
    ```


```
open index.html
```
