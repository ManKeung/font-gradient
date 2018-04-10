# 字体渐变

1. 01.html --> [demo1](https://mankeung.github.io/font-gradient/src/01.html)
2. 02.html --> [demo2](https://mankeung.github.io/font-gradient/src/02.html)


## demo1

background: linear-gradient(to right, red, blue); 这行是给背景设置为渐变色，这里注意一点，这样是简写了，其实是给background-image 设置为渐变色，不是 background-color ，是背景图 取值为渐变色，如果不知道渐变色，直接到这里看， [CSS3 渐变（Gradients）](http://www.runoob.com/css3/css3-gradients.html)

-webkit-background-clip: text; 这行就要说到，background-clip 属性了 ，我们来看看 [W3Cschool](http://www.w3school.com.cn/cssref/pr_background-clip.asp) 上的说明

> background-clip 属性 规定背景的绘制区域

+ 语法
`background-clip: border-box|padding-box|content-box;`

值 | 描述
---- | ----
border-box | 背景被裁剪到边框盒。
padding-box | 背景被裁剪到内边距框。
content-box | 背景被裁剪到内容框。

上面没有说取值 text 的情况，看到前面的前缀，大家应该也能想到，它的兼容性问题了，目前还不是能所有浏览器都支持。

取值为text的意思，就是以区块内的文字作为裁剪区域向外裁剪，文字的背景即为区块的背景，文字之外的区域都将被裁剪掉。

所以，我们最后写color: transparent; 让文字为透明色，就是让后面背景色显示出来。

## demo2

> :before 选择器向选定的元素 前 插入内容。
> 使用content 属性来指定要插入的内容。

content取值 attr 就是用来获取属性值的，content:attr(属性名);

content: attr(text); 能获取到元素的 text 属性，这里的这个text属性是自己自定义的一个属性，你也可以在元素中加一个 tt 属性，像这样
<\h1 text="字体渐变测试文本">字体渐变测试文本<\/h1>
然后content属性 这样写，content: attr(tt); 同样是可以起作用的。

好的我们继续说第二种方式的重点，mask属性，因为之前已经写过一篇介绍mask属性的文章了，
[简单说 CSS中的mask—好好利用mask-image](https://segmentfault.com/a/1190000011838367)
这里就不很详细的介绍了，想详细了解的朋友可以看看上面这篇文章，一定会对你有所帮助的。

mask属性简单说，就是能让元素的某一部分显示或隐藏。
我们看张图就能明白，第二种方式实现的原理了
