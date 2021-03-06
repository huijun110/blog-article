hasLayout
===========================
很多时候，CSS在IE下的解释十分奇怪，明明在Firefox下显示的非常正确，但到了IE下却出现了问题，有时候，这些问题甚至表的非常诡异——例如，一个比较经典的BUG就是设置border的时候，有时候border会断开，刷新页面或者滚动页面的时候，断掉的部分又会重新连接起来。

这些诡异的问题往往大部分和IE下的一个神秘的属性相关——hasLayout。

hasLayout是IE下的一个转有属性，用于CSS的解释引擎。有时候在IE下一些复杂的CSS设置解释起来会出现BUG，其原因可能是与hasLayout没有被自动触发有关，我们通过一些技巧，手动触发hasLayout属性就可以解决BUG了。这也算是针对IE下疑难杂症的特殊偏方了，很多时候，触发了hasLayout就可以药到病除了。

hasLayout的触发方法有很多种，例如设置width、height值，设置position为relative等。但如果设置了width、height或position都会触发hasLayout的同时带来一些副作用的。早期的工程师推荐使用“height：1%”来触发hasLayout，那时候还没有出现IE7，而height属性在IE6下其实是按照“min-height”来解释的，所以只要针对IE6进行hack，“* html{height:1%}”就可以触发hasLayout，同时又不带来副作用。后来出现的IE7任然存在很多hasLayout方面的问题，但IE7已经能够正确识别height属性了，“height：1%”的方法也就不再适用了。

于是，一个更好的方法开始流行了，它使用了一个生僻的CSS属性zoom来触发hasLayout——“zoom：1“可以触发hasLayout，并且不会像height等属性一样引入副作用，更妙的是，我们可以不用CSS hack了。但“zoom”并不是一定可以触发hasLayout的，在极少数的情况下，例如非常复杂的CSS设置，特别是使用DHTML的时候，使用“zoom：1”有时候也会无效，这时，我们可能需要借助更为强大的“position：relative”来帮助触发hasLayout，总之，“zoom”是最常用、最安全、成本最小的触发hasLayout的方式，一般情况下，使用它完全可以触发hasLayout了。如果遇到很特殊的情况，“zoom：1”无效的情况下，我们可以通过设置“position：relative”来触发hasLayout，尽管他会带来一点副作用。

值得强调的是，hasLayout的涉及初衷是用于辅助块级元素的盒模型解释的，他是用于块级元素的。如果用于行内元素，会引发一些特殊的效果。

值得庆幸的是，随着微软window10的推出，与之相伴的新浏览器斯巴达横空出世，IE成为永远的历史，不得不说，专治IE的各种私人解决方案会失效，我们不再需要为IE的各种诡异问题感到头痛，拥抱Webkit等新浏览器内核，相信前端WEB页面的工作会随Firefox一样，令人舒服（本人觉得Firefox是最懂开发者心的浏览器）。

块级元素和行内元素的区别
------------------------------
块级元素和行内元素是布局的最基本的两种元素，常见的块级元素有div、p、form、ul、li、ol等，常见的额行内元素有span、strong、em等。

块级元素和行内元素有什么区别呢？块级元素会独占一行，默认情况下，其宽度自动填满其父容器元素宽度，行内元素不会独占一行，相邻的元素排列在同一行中，直到一行拍不下才会换行，其宽度随元素的内容而变化。如如下代码：
```html
<style type="text/css">
p{background-color: red;}
div{background-color: yellow}
span{background-color: blue}
strong{background-color: green}
</style>

<p>块级元素P</p><div>块级元素DIV</div><span>行内元素span</span><strong>行内元素strong</strong>
```

在浏览器中的效果如下图：  
![Paste_Image.png](../image/1604/css2/1.png)

块级元素可以设置width、height属性，行内元素设置width、height属性无效。如下面代码：
```html
<style type="text/css">
p{background-color: red;width: 200px;height: 200px;}
div{background-color: yellow;width: 400px;height: 10px;}
span{background-color: blue;width: 200px;height: 200px;}
strong{background-color: green;width: 400px;height: 100px;}
</style>

<p>块级元素P</p><div>块级元素DIV</div><span>行内元素span</span><strong>行内元素strong</strong>
```

在浏览器中的效果如下图:  
![Paste_Image.png](../image/1604/css2/2.png)

注意，块级元素即使设置了宽度，任然是独占一行的。

块级元素可以设置margin和padding属性。行内元素的margin、padding属性很奇怪，水平方向的padding- left、padding-right、margin-left、margin-right都产生边距效果，但 6方向的padding-top、padding-bottom、margin-top、margin-bottom却不会产生边距效果。如下代码：
```html
<style type="text/css">
p{background-color: red;padding: 20px;margin: 20px;}
div{background-color: yellow;padding: 20px;}
span{background-color: blue;padding: 20px;margin: 20px;}
strong{background-color: green;padding: 20px;margin: 20px;}
</style>

<p>块级元素P</p><div>块级元素DIV</div><span>行内元素span</span><strong>行内元素strong</strong>
```

在浏览器中的效果如图：  
![Paste_Image.png](../image/1604/css2/3.png)

如上图所示，竖直方向的margin看不到任何效果，竖直方向的padding虽然增加了，但却并没有和相邻的元素拉开距离。

块级元素和行内元素的CSS相关属性是display，其中块级元素对应于display：block，行内元素对应于display：inline。我们可以通过修改display属性来切换块级元素和行内元素，如下面代码：
```html
<style type="text/css">
p{background-color: red;display: inline;}
div{background-color: yellow;display: inline;}
span{background-color: blue;display: block;}
strong{background-color: green;display: block;}
</style>

<p>块级元素P</p><div>块级元素DIV</div><span>行内元素span</span><strong>行内元素strong</strong>
```

在浏览器中的效果如图：  
![Paste_Image.png](../image/1604/css2/4.png)