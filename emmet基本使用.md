# 编辑器插件**emmet** 的使用技巧
Emmet是一款编辑器插件，支持多种编辑器支持。在前端开发中，Emmet 使用缩写语法快速编写 HTML、CSS 以及实现其他的功能，极大的提高前端开发效率

#### 下载地址[http://emmet/io/download](http://emmet/io/download)

## 1. 使用 **>** 生成元素子节点
```
div>ul>li
```
相当于：
```html
<div>
    <ul>
        <li></li>
    </ul>
</div>
```
## 2. 使用 **+** 生成元素的兄弟节点
```
div+p+bq
```
相当于：
```html
<div></div>
<p></p>
<blockquote></blockquote>
```
## 3. 使用 **^** 可以在父级生成新节点
```
div>div>p>span+em^bq
```
相当于：
```html
<div>
    <div>
        <p>
            <span></span><em></em>
        </p>
        <blockquote></blockquote>
    </div>
</div>
```
## 4. 使用 **\*** 生成多个相同的节点
```
ul>li*5
```
相当于：
```html
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```
## 5. 使用圆括号 **()** 可以实现复杂的DOM结构
```
div>(header>ul>(li>a)*2)+footer>p
```
相当于：
```html
<div>
    <header>
        <ul>
            <li><a href=""></a></li>    
            <li><a href=""></a></li>
        </ul>
    </header>
    <footer>
        <p></p>
    </footer>
</div>
```
## 6. 给元素添加ID和CLASS属性与CSS语法相同
```
div#header+div.page+footer.class1.class2.class3
```
相当于：
```html
<div id="header"></div>
<div class="page"></div>
<footer class="class1 class2 class3"></div>
```
## 7. 使用 **[attr]** 来自定义属性
```
a[href="www.xxx.com"][title="hello world!"]
```
相当于：
```html
<a href="www.xxx.com" title="hello world!"></a>
```
## 8. 使用 **$** 可以对重复元素进行有序编号
```
ul>li.item$*5
```
相当于：
```html
<ul>
    <li class="item1"></li>
    <li class="item2"></li>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
</ul>
```
## 9. 使用 **{}** 可以给元素添加文本内容
```
a{click me}
```
相当于：
```html
<a href="">click me</a>
```