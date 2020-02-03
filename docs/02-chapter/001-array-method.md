# array method

## forEach
```js
numbers.forEach(function (x) {
  console.log(x % 2 == 0);
}); 
```

## 使用for...of循环迭代
```js
for (let n of numbers) {
 console.log((n % 2 == 0) ? 'even' : 'odd');
}


// iterators
var arr = [1,2,3]
var ab = arr.entries();
for(var a of ab){
    console.log(a);
}
```

## 使用ES6新的迭代器（@@iterator）
arr[Symbol.iterator] 可以取得这个属性
<!-- 实际的结构 -->
next().value => { value: xxx, done: true/false };

```js
let iterator = numbers[Symbol.iterator]();
console.log(iterator.next().value); // 1
console.log(iterator.next().value); // 2
console.log(iterator.next().value); // 3
console.log(iterator.next().value); // 4
console.log(iterator.next().value); // 5 
console.log(iterator.next().value); // undefined 
```

## entries
```js
let aEntries = numbers.entries(); // 得到键值对的迭代器
console.log(aEntries.next().value); // [0, 1] - 位置0的值为1
console.log(aEntries.next().value); // [1, 2] - 位置1的值为2
console.log(aEntries.next().value); // [2, 3] - 位置2的值为3


let aValues = numbers.values();
console.log(aValues.next()); // {value: 1, done: false }
console.log(aValues.next()); // {value: 2, done: false }
console.log(aValues.next()); // {value: 3, done: false } 
```

## 根据传入的参数创建数组
```js
let numbers3 = Array.of(1);
let numbers4 = Array.of(1, 2, 3, 4, 5, 6); 
```

## 将空数组填充
```js
numbersCopy.fill(0); 
```
