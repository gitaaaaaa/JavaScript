6种数据类型:  
基本数据类型:
<a href="#number">Number</a> 
<a href="#string">String</a> 
<a href="#boolean">Boolean</a>
<a href="#undefined">Undefined</a> 
<a href="#null">Null</a>  
复杂数据类型: <a href="#object">Object</a>

typeof 操作符 -- 来检测给定变量的数据类型

1. "undefined"——如果这个值未定义；
2. "boolean"——如果这个值是布尔值；
3. "string"——如果这个值是字符串；
4. "number"——如果这个值是数值；
5. <font color=red>"object"——如果这个值是对象或 null；<font>
6. "function"——如果这个值是函数

### <a name="number">Number</a>
```
typeof(1); // number
```

### <a name="string">String</a>
```
typeof("字符串"); // string
```
### <a name="boolean">Boolean</a>
```
typeof(true); // boolean
```
### <a name="undefined">Undefined</a>
```
Undefined是为了正式区分空对象指针与未经初始化的变量
```
### <a name="null">Null</a>
```
 null为空指针对象,不能像普通对象一样直接添加属性
```
<a href="#checkNullObj"> {} 与 null 的区别</a>  

### <a name="object">Object</a>




####<a name="checkNullObj">判断对象是否为空对象 js</a> 


1. 最常见的思路，for...in...遍历属性，为真则为“非空数组”；否则为“空数组”
```javascript
for(var i in obj) { // 如果不为空，则会执行到这一步，返回true
        return true
    }
    return false;// 如果不为空，则会执行到这一步，返回true
```
   

2. 通过JSON自带的stringify()方法来判断:
```javascript
if (JSON.stringify(data) === '{}') {
    return false // 如果为空,返回false
}
return true // 如果不为空，则会执行到这一步，返回true
```

3.ES6新增的方法Object.keys():
```
if (Object.keys(object).length === 0) {
    return false // 如果为空,返回false
}
return true // 如果不为空，则会执行到这一步，返回true
```



