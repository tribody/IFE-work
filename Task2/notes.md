#层叠和样式

对于层叠来说，共有三种主要来源：

* 浏览器对HTML定义的默认样式
* 用户定义的样式
* 开发者定义的样式，可以有三种形式:
 + 定义在外部文件（外联样式）
 + 在页面的头部定义（内联样式）：只在本页面内生效
 + 定义在特定的元素身上（行内样式）：多用于测试，可维护性差

优先级：网页开发者定义的样式>网页阅读者定义的样式>浏览器的默认样式

## 选择器

* 类选择器：通过设置元素的 class 属性，可以为元素指定类名。类名由开发者自己指定。 文档中的多个元素可以拥有同一个类名。在写样式表时，类选择器是以英文句号（.）开头的。
* ID选择器：通过设置元素的 id 属性为该元素制定ID。ID名由开发者指定。每个ID在文档中必须是唯一的。在写样式表时，ID选择器是以#开头的。

优先级，ID选择器>类选择器>标签选择器。冲突规则后出现的规则优先级高（就近原则）。

### 伪类选择器
CSS伪类（pseudo-class）是加在选择器后面的用来指定元素状态的关键字。比如，:hover 会在鼠标悬停在选中元素上时应用相应的样式。

伪类和伪元素（pseudo-elements）不仅可以让你为符合某种文档树结构的元素指定样式，还可以为符合某些外部条件的元素指定样式：浏览历史(比如是否访问过 (:visited)， 内容状态(如 :checked ), 鼠标位置 (如:hover). 

### 基于关系的选择器

|选择器|选择的元素|
|:------:|:------------|
|A E|元素A的任一后代元素E (后代节点指A的子节点，子节点的子节点，以此类推)|
|A > E|元素A的任一子元素E(也就是直系后代)|
|E:first-child|任一是其父母结点的第一个子节点的元素E|
|B + E|元素B的任一下一个兄弟元素E|
|B ~ E|B元素后面的拥有共同父元素的兄弟元素E|

（*）可以用来表示任意元素。

基于关系的选择器和伪类选择器构造纯CSS下拉菜单，示例：

``` css
div.menu-bar ul ul {
  display: none;
}

div.menu-bar li:hover > ul {
  display: block;
}
```

``` html
<div class="menu-bar">
  <ul>
    <li>
      <a href="example.html">Menu</a>
      <ul>
        <li>
          <a href="example.html">Link</a>
        </li>
        <li>
          <a class="menu-nav" href="example.html">Submenu</a>
          <ul>
            <li>
              <a class="menu-nav" href="example.html">Submenu</a>
              <ul>
                <li><a href="example.html">Link</a></li>
                <li><a href="example.html">Link</a></li>
                <li><a href="example.html">Link</a></li>
                <li><a href="example.html">Link</a></li>
              </ul>
            </li>
            <li><a href="example.html">Link</a></li>
          </ul>
        </li>
      </ul>
    </li>
  </ul>
</div>
```