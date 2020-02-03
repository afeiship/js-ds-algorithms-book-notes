# stack
> 栈.
> 栈是一种遵从后进先出（LIFO）原则的有序集合.

- 新添加的或待删除的元素都保存在栈的同一端，称作栈顶
- 另一端就叫栈底。
- 在栈里，新元素都靠近栈顶，旧元素都接近栈底。
- 栈也被用在编程语言的编译器和内存中保存变量、方法调用等

## base-converter(进制转换)
![](https://tva1.sinaimg.cn/large/006tNbRwgy1gbjfdndg5xj311x0u0jym.jpg)

```js
function baseConverter(decNumber, base) {
  var remStack = new Stack(),
    rem,
    baseString = '',
    digits = '0123456789ABCDEF'; //{6}
  while (decNumber > 0) {
    rem = Math.floor(decNumber % base);
    remStack.push(rem);
    decNumber = Math.floor(decNumber / base);
  }
  while (!remStack.isEmpty()) {
    baseString += digits[remStack.pop()]; //{7}
  }
  return baseString;
}
```

## resources
- https://github.com/afeiship/next-stack
