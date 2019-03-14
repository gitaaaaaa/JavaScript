```questions1
function Foo() {
    getName = function () { alert (1); };
    return this;
}
Foo.getName = function () { alert (2);};
Foo.prototype.getName = function () { alert (3);};
var getName = function () { alert (4);};
function getName() { alert (5);}

//请写出以下输出结果：
Foo.getName();          
getName();              
Foo().getName();      
getName();              
new Foo.getName();     
new Foo().getName();   
new new Foo().getName();
```

涉及知识点:变量定义提升、this 指针指向、运算符优先级、原型、继承、全局变量污染、对象属性及原型属性优先级等知识

## 解析

1. 函数提升，函数优先
```函数提升，函数优先
function Foo() {
    getName = function () { alert (1); };
    return this;
}
function getName() { alert (5);} // 提升
Foo.getName = function () { alert (2);};
Foo.prototype.getName = function () { alert (3);};
var getName = function () { alert (4);};

```

### 问题一
```
 Foo.getName(); // 2
```
这是一个简单的对象属性访问的问题，可能有小伙伴会误认为3，如果在 getName 不是直接存在于 Foo 中，才会遍历[[Prototype]] 链，这时候才会取 Foo.prototype.getName。（即函数3）  ???

### 问题二
```
getName();   // 4
```
在对程序在编译阶段的行为的分析中，经过函数提升，我们可以知道最后 getName() 被赋值为函数4 

### 问题三
