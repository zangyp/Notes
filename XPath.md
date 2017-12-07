# XPath
XPath 是一门在 XML 文档中查找信息的语言。  
  
## XPath 术语
### 节点
在 XPath 中，有七种类型的节点：元素、属性、文本、命名空间、处理指令、注释以及文档（根）节点。  
XML文档是被作为节点树来对待的。树的根被称为文档节点或者根节点。  
  
```xml
 <?xml version="1.0" encoding="UTF-8"?>

<bookstore>
  <book>
    <title lang="en">Harry Potter</title>
    <author>J K. Rowling</author>
    <year>2005</year>
    <price>29.99</price>
  </book>
</bookstore> 
```
上面的XML文档中的节点例子：
```xml
<bookstore> (文档节点)

<author>J K. Rowling</author> (元素节点)

lang="en" (属性节点) 
```
  
### 基本值（或称原子值，Atomic value）
基本值是无父或无子的节点。比如：
  
```
J K. Rowling

"en" 
```
  
### 项目（Item）
项目是基本值或者节点。  
  
## 节点关系
### 父节点（parent）
每个元素以及属性都有一个父。  
  
在下面的例子中，book 元素是 title、author、year 以及 price 元素的父：
```xml
 <book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book> 
```
  
### 子节点（children）
元素节点可有零个、一个或多个子。  
  
在下面的例子中，title、author、year 以及 price 元素都是 book 元素的子：
```xml
<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book> 
```
  
### 同胞（sibling）
拥有相同的父的节点  
  
在下面的例子中，title、author、year 以及 price 元素都是同胞：
```xml
<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book> 
```
  
### 先辈（Ancestor） 
某节点的父、父的父，等等。  
  
在下面的例子中，title 元素的先辈是 book 元素和 bookstore 元素：
```xml
<bookstore>

<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>

</bookstore> 
```
  
### 后代（Descendant） 
某个节点的子，子的子，等等。  
  
在下面的例子中，bookstore 的后代是 book、title、author、year 以及 price 元素：
```xml
<bookstore>

<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>

</bookstore> 
```
  
## 语法
XPath 使用路径表达式来选取 XML 文档中的节点或节点集。节点是通过沿着路径 (path) 或者步 (steps) 来选取的。
### XML实例文档
我们将在下面的例子中使用这个 XML 文档。  
```XML
 <?xml version="1.0" encoding="UTF-8"?>

<bookstore>

<book>
  <title lang="eng">Harry Potter</title>
  <price>29.99</price>
</book>

<book>
  <title lang="eng">Learning XML</title>
  <price>39.95</price>
</book>

</bookstore>
```
  
### 选取节点
XPath 使用路径表达式在 XML 文档中选取节点。节点是通过沿着路径或者 step 来选取的。 下面列出了最有用的路径表达式：  

| 表达式 | 描述 |  
| ----- | ----- |  
| nodename | 选取此节点的所有子节点。 |  
| / | 从根节点选取。 |  
| // | 从匹配选择的当前节点选择文档中的节点，而不考虑它们的位置。 |  
| . | 选取当前节点。 |  
| .. | 选取当前节点的父节点。 |  
| @ |  	选取属性。 |  
