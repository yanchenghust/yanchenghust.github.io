---
author: wdd
categories: [fe, svg]
tags: [loading, fe, svg]
---
# loading图标实现
## 代码实现
{% highlight javascript %}
<div>
  <i>
    <svg  viewBox="0 0 1096 1096"class="anticon-spin" data-icon="loading" width="2em" height="2em" fill="currentColor" aria-hidden="true"><path d="M988 548c-19.9 0-36-16.1-36-36 0-59.4-11.6-117-34.6-171.3a440.45 440.45 0 0 0-94.3-139.9 437.71 437.71 0 0 0-139.9-94.3C629 83.6 571.4 72 512 72c-19.9 0-36-16.1-36-36s16.1-36 36-36c69.1 0 136.2 13.5 199.3 40.3C772.3 66 827 103 874 150c47 47 83.9 101.8 109.7 162.7 26.7 63.1 40.2 130.2 40.2 199.3.1 19.9-16 36-35.9 36z"></path></svg>
  </i>
  <span>loading</span>
</div>

{% endhighlight %}
## 知识点
### `<i>`元素设置图标
为什么使用`<i>`来设置图标，事实上`<i>`元素语义上并不适合用来做图标，但是由于`<i>`元素所占用的空间比`<span>`还要少(事实上我们完全可以用`<span>`来设置图标)，所以比较节省空间，而且使用`<i>`元素只为添加一个图标是为了分开图标和内容，为了更好的布局，否则，我们也完全可以直接在内容前面添加图标即可！！

### svg标签的viewBox属性
刚上手的时候遇到了SVG下面的path很大，超出显示区域，可以尝试设置下svg的width，height为很大的值，暂时让她显示出来一部分，告诉自己图标过大，而不是程序bug未显示。然后通过设置viewBox属性的值来缩小图标。
viewBox的四个参数分别代表：最小X轴数值；最小y轴数值；宽度；高度。
![aaa](https://github.com/yhddx/Practice/blob/master/pics/svg.jpg?raw=true)

### c 动画

设置为“旋转”，from：“角度 x坐标 y坐标”，to：“角度 x坐标 y坐标”，dur=“持续时间”，repeatCount=“重复次数”
{% highlight javascript %}
<animateTransform attributeName="transform" type="rotate" from="0 548 548" to="360 548 548" dur="1s" repeatCount="indefinite" />
{% endhighlight %}

