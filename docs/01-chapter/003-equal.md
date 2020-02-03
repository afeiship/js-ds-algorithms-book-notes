# equal

## 放在 if里的条件隐式判断

~~~
数值类型 转换成布尔值
undefined false
null false
布尔值 true是true，false是false
数字 +0、-0和NaN都是false，其他都是true
字符串 如果字符串是空的（长度是0）就是false，其他都是true
对象 true 
~~~


## 相等操作符 (== 的隐式操作)
```js
x == toNumber('abc') 
```
~~~
类型（x） 类型（y） 结 果
null undefined true
undefined null true
数字 字符串 x == toNumber(y)
字符串 数字 toNumber(x) == y
布尔值 任何类型 toNumber(x) == y
任何类型 布尔值 x == toNumber(y)
字符串或数字 对象 x == toPrimitive(y)
对象 字符串或数字 toPrimitive(x) == y
~~~


## 兼容性列表
- ES6：http://kangax.github.io/compat-table/es6/
- ES7：http://kangax.github.io/compat-table/es7/

## 浏览器里支持的选项
chrome://flags


## 这里的隐式转化可以这样理解
```js
// Symbol.toPrimitive 是一个预定义的 Symbol值
const object1 = {
  [Symbol.toPrimitive](hint) {
    if (hint == 'number') {
      return 42;
    }
    return null;
  }
};

console.log(+object1);
// expected output: 42
```
