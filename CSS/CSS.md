# CSS基础
CSS(Cascading Style Sheets) 层叠样式表，是一种用于描述HTML或XML文档外观和格式的样式表语言。通过选择器选择元素，并为其应用样式规则。
```css
selector {
    property: value;
}
```
## CSS选择器
### 基本选择器
- 元素选择器
- 类选择器
- ID选择器
- 属性选择器
- 伪类选择器
- 伪元素选择器  
#### 元素选择器
通过HTML元素名称选择元素
```css
/*选择所有的 p元素*/
p {

}
/*选择所有的 div元素*/
div {
    
}
```
#### 类选择器
通过HTML元素的`class`属性选择元素
```css
/*选择所有class属性为my_class的元素*/
.my_class {
    
}
```
#### ID选择器
通过HTML元素的`id`属性选择元素
```css
/*选择所有id属性为my_id的元素*/
#my_id {

}

```
#### 属性选择器
根据元素的某个属性存在或者属性值选择元素
```css
/*选择所有title属性存在的a的元素*/
a[title] {
    
}
/*选择所有title属性值为"my_title"的a的元素*/
a[title="my_title"] {
    
}
```
#### 伪类选择器
选择某个状态的元素
```css
/*选择所有a元素的第一个子元素*/
a:first-child {
    
}
/*选择指针悬停在上的a元素*/
a:hover {
    
}
```
#### 伪元素选择器
选择某个元素的某个部分
```css
/*选择所有p元素的第一个字母*/
p::first-letter {
    
}
/*选择所有p元素的第一个行*/
p::first-line {
    
}
```

### 组合列表
通过多个选择器来选择特定的元素
```css
/*选择所有class属性为my_class的p元素*/
p.my_class {
    
}
/*选择所有id属性为my_id的div元素*/
div#my_id {
    
}
```
#### 后代选择器
用于选择某个元素的所有后代元素
```css
/*语法*/
ancestor descendant {

}

/*选择所有div元素的所有后代p元素*/
div p {
    
}

```
#### 子选择器
用于选择某个元素的直接子元素
```css
/*语法*/
parent > child {
    
}

/*选择所有div元素的直接子p元素*/
div > p {
    
}
```
#### 相邻兄弟选择器
用于选择某个元素之后的第一个同级兄弟元素
```css
/*语法*/
prev + next {
    
}
/*选择所有div元素之后的第一个同级p元素*/
div + p {
    
}
```
#### 通用兄弟选择器
用于选择某个元素之后的所有同级兄弟元素
```css
/*语法*/
prev ~ siblings {
    
}
/*选择所有div元素之后的所有同级p元素*/
div ~ p {
    
}

```
#### 组合选择器的优先级
1. 后代选择器：优先级较低，因为选择范围较广。
2. 子选择器：优先级稍高，因为选择范围更具体。
3. 相邻兄弟选择器：优先级较高，因为选择范围非常具体。
4. 通用兄弟选择器：优先级介于相邻兄弟选择器和子选择器之间。 
   

# CSS样式基础
## 样式规则
CSS样式规则由选择器和声明块组成。选择器指定要应用样式的元素，声明块包含一个或多个样式声明，每个声明由属性和值组成。
```css
selector {
    property1: value1;
    property2: value2;
    /* 更多属性 */
}
```
## 样式优先级
当多个样式规则应用于同一个元素时，CSS会根据以下优先级规则来确定最终应用的样式：
1. **行内样式**：直接在HTML元素中使用`style`属性定义的样式，优先级最高。
2. **ID选择器**：通过`id`属性选择的元素，优先级次之。
3. **类选择器、属性选择器、伪类选择器**：这些选择器的优先级相同，低于ID选择器。
4. **元素选择器、伪元素选择器**：这些选择器的优先级最低。
5. **继承**：某些样式会从父元素继承到子元素，继承的样式优先级最低。

## 样式冲突解决
当多个样式规则冲突时，CSS会根据优先级规则来决定应用哪个样式。如果优先级相同，则后定义的样式会覆盖先定义的样式。

# CSS文本样式
## 字体样式
可以使用`font-family`、`font-size`、`font-weight`等属性来设置字体样式。
```css
/* 设置字体家族 */
p {
    font-family: Arial, sans-serif;
}

/* 设置字体大小 */
h1 {
    font-size: 24px;
}

/* 设置字体粗细 */
strong {
    font-weight: bold;
}
```

## 文本颜色
使用`color`属性来设置文本颜色。
```css
/* 设置文本颜色为红色 */
.red-text {
    color: red;
}

/* 使用十六进制颜色值 */
.hex-color {
    color: #ff0000;
}

/* 使用RGB颜色值 */
.rgb-color {
    color: rgb(255, 0, 0);
}
```

## 文本对齐
使用`text-align`属性来设置文本对齐方式。
```css
/* 左对齐 */
.left-align {
    text-align: left;
}

/* 右对齐 */
.right-align {
    text-align: right;
}

/* 居中对齐 */
.center-align {
    text-align: center;
}

/* 两端对齐 */
.justify-align {
    text-align: justify;
}
```

## 文本装饰
使用`text-decoration`属性来设置文本装饰，如下划线、删除线等。
```css
/* 添加下划线 */
.underline {
    text-decoration: underline;
}

/* 添加删除线 */
.strike-through {
    text-decoration: line-through;
}

/* 添加上划线 */
.overline {
    text-decoration: overline;
}
```

## 文本转换
使用`text-transform`属性来控制文本的大小写转换。
```css
/* 转换为大写 */
.uppercase {
    text-transform: uppercase;
}

/* 转换为小写 */
.lowercase {
    text-transform: lowercase;
}

/* 首字母大写 */
.capitalize {
    text-transform: capitalize;
}
```

## 字间距和行高
使用`letter-spacing`和`line-height`属性来调整字间距和行高。
```css
/* 设置字间距为2px */
.letter-spacing {
    letter-spacing: 2px;
}

/* 设置行高为1.5倍 */
.line-height {
    line-height: 1.5;
}
```

# CSS排版
## 盒模型
每个HTML元素都可以看作是一个矩形盒子，包含内容、内边距、边框和外边距。
- **内容**：元素的实际内容区域。
- **内边距**：内容与边框之间的空间。
- **边框**：围绕内容和内边距的边框。
- **外边距**：元素与其他元素之间的空间。

## 布局方式
### 浮动布局
使用`float`属性来实现浮动布局。
```css
/* 左浮动 */
.float-left {
    float: left;
}

/* 右浮动 */
.float-right {
    float: right;
}
```

### 定位布局
使用`position`属性来实现定位布局。
```css
/* 相对定位 */
.relative {
    position: relative;
    top: 10px;
    left: 10px;
}

/* 绝对定位 */
.absolute {
    position: absolute;
    top: 50px;
    left: 50px;
}

/* 固定定位 */
.fixed {
    position: fixed;
    bottom: 0;
    right: 0;
}
```

### Flexbox布局
Flexbox是一种现代的布局模式，可以轻松实现复杂的布局。
```css
/* 定义Flex容器 */
.flex-container {
    display: flex;
    justify-content: center; /* 水平居中 */
    align-items: center; /* 垂直居中 */
}

/* 定义Flex项目 */
.flex-item {
    flex: 1; /* 项目占据剩余空间的比例 */
    margin: 10px;
}
```

## 响应式设计
使用媒体查询来实现响应式设计，使页面在不同设备上显示合适的布局。
```css
/* 在屏幕宽度小于768px时应用的样式 */
@media (max-width: 768px) {
    body {
        background-color: lightblue;
    }
    
    .container {
        flex-direction: column;
    }
}
```


