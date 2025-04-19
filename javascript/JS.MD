# JavaScript 核心知识笔记

## 一、基础语法
### 1.1 变量声明
js为弱类型语言，变量无需声明类型，直接赋值即可。
```javascript
// 传统方式
var name = "张三"; 

// ES6+ 推荐方式
let age = 25;        // 可重新赋值
const PI = 3.14;     // 常量不可变
```
特性对比表：

| 声明方式 | 作用域   | 重复声明 | 变量提升 |
|----------|----------|----------|----------|
| var      | 函数级   | ✅允许    | ✅存在    |
| let      | 块级     | ❌禁止    | ❌不存在   |
| const    | 块级     | ❌禁止    | ❌不存在   |

1.2 数据类型
```javascript
// 原始类型
typeof "Hello"      // "string"
typeof 42           // "number"
typeof true         // "boolean"
typeof undefined    // "undefined"

// 引用类型
const arr = [1,2,3];
const obj = { key: "value" };
```

---

二、ES6+ 核心特性
2.1 箭头函数
```javascript
// 传统函数
function sum(a, b) { return a + b }

// 箭头函数（自动绑定外层this）
const sum = (a, b) => a + b;
const square = n => n * n;
```

2.2 解构赋值
```javascript
// 数组解构
const [first, second] = [10, 20];

// 对象解构
const { name, age } = userProfile;
```

2.3 模板字符串
```javascript
const greeting = `用户${name}，欢迎加入！
您的注册时间是：${new Date().toLocaleString()}`;
```

---

三、DOM操作范式
3.1 元素选择
```javascript
// 常用选择器
document.querySelector('#header');      // ID选择
document.querySelectorAll('.item');     // 类选择
```

3.2 事件处理
```javascript
// 事件监听最佳实践
element.addEventListener('click', (e) => {
  console.log(`点击坐标: (${e.clientX}, ${e.clientY})`);
});
```

---

四、异步编程
4.1 Promise链式调用
```javascript
fetch('/api/data')
  .then(response => response.json())
  .then(data => render(data))
  .catch(error => console.error('请求失败:', error));
```

4.2 async/await
```javascript
async function loadUserData() {
  try {
    const response = await fetch('/users/1');
    const data = await response.json();
    return data;
  } catch (error) {
    handleError(error);
  }
}
```

---

五、调试与优化
5.1 调试技巧
```javascript
console.table([{id:1,name:'A'}, {id:2,name:'B'}]);  // 表格化输出
console.time('loop');  // 性能计时
// ...代码块
console.timeEnd('loop');
```

5.2 模块化开发
```javascript
// 导出模块
export const utils = {
  formatDate: (timestamp) => {/*...*/}
};

// 导入模块
import { utils } from './helpers.js';
```

---

工具推荐：  
• 编辑器：VS Code（支持实时预览与Lint校验）  

• 文档生成：JSDoc + Markdown插件  

• 在线演练场：JSFiddle/CodePen


---

> 持续迭代建议：  
> 1. 建立「代码片段库」区块，收集常用工具函数  
> 2. 添加「设计模式」章节，记录单例/观察者等模式实现  
> 3. 补充「性能优化」专项，包含内存管理、防抖节流等

此模板通过层级化结构组织知识点，结合代码块、表格等元素提升可读性，建议配合Typora等支持大纲视图的编辑器使用，实现高效检索与更新。