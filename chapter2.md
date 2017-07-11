# 第 2 章
# 20
GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

## 21

![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/25.jpg "百度logo")

## 22
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/26.jpg "百度logo")

选抒器足jQuery的根接，在jQuery中，对事件处理、遍历DOM和Ajax操作都依 赖于选杼器。如采能熟练地使用选杼器，不仅能简化代码，而且可以达到事半功倍的 效果。

### 21

#### 1.CSS选择器  
在开始学习jQuery选择器之前，有必要简单了解前儿年流行起来的CSS (Cascading Style Sheets，层脅样式表）技术。  
CSS适一项出色的技术，它使得网页的结构和表现样式完全分离。利用CSS选择器能轻 松地对某个元素添加样式而不改动HTML结构，只需通过添加不同的CSS规则，就可以得 到各种不同样式的M页。  
耍使菜个样式应用于特定的HTML元素，首先需要找到该元素。在CSS中，执行这一 任务的表现规则称为CSS选杼器。学会使用CSS选择器是学习CSS的基础，它为在获取目 标元素之后施加样式提供了极大的灵活性。常用的CSS选择器分类如表2-1所示。  

|---|---|---|---|
|选择器|语法|描述|示例|
|---|---|---|---|
|---|---|---|---|

儿乎所W主流浏览器都支持L:面这些常川的选择器。此外CSS屮还有伪类选杼器 (E:Pseudo-Elements{ CssRules })、子选择器(E > F{ CssRules })、临近选杼器(E + F {CssRules})和属性选杼器(E[attr] {CssRules})等。但遗憾的是，主流浏览器并非完全支持 所有的CSS选择器。


更加详细的介绍可以参考 

http://www.w3.org/TR/CSS2/selector.html 网址。
了解这些相关知识后，來#一个有关CSS类选择器的简单例子，代码如下：
```style
<p style=,'color: red; font-size: 30px; ">CSS Demo</p>
```
l：面代码的意思是将<p>元素里的文本颜色设背为红色，字体大小设置为30px。
像L面这样把CSS代码和HTML代码混杂在一起的做法足非常不妥的，它并不符合表 现和内容相分离的设计原则，因此建议使用下面的方法，代码如下：
```style
.demo{	//给class为demo的元素添加样式
color:red; font-size:30px;
}
```
```
<p class=ndemo">CSS Demo.</p>
```
«< ««< 第j章jQuery选择器
先把样式写在<style>标签里，然后用class M性将元素和样式联系起來，class作为连接 样式和网页结构的纽带。这样的写法不仅容易理解和阅读，而且当需要改变一些样式的时 候，只要^<style>#签里改变相关的样式即可。
例如耍使所有class为demo的<p>元素里的字体加粗，可以直接在<style>里编写，而不 需要去网页串.寻找所柯class为demo的<p>元素再逐个添加样式，代码如下：
<style>
.demo{	//给class为demo的元素添加样式
color:red; font-size:30px; font-weight: bold;	/ / 字体加粗
)
</style>
<p class=ndemo">CSS Demo.</p>
H 把CSS应用到网页中有3种方式，即行间样式表、内部样式表和外部样式表。





## 23

![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/27.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/28.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/29.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/30.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/31.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/32.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/33.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/34.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/35.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/36.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/37.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/38.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/39.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/40.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/41.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/42.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/43.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/44.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/45.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/46.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/47.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/48.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/49.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/50.jpg "百度logo")

## 24  

![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/51.jpg "百度logo")

## 26  

![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/52.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/53.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/54.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/55.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/56.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/57.jpg "百度logo")

## 27  

![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/58.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/59.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/60.jpg "百度logo")
![baidu](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/2/61.jpg "百度logo")