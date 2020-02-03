# priority queue

## 定义
元素的添加和移除是基于优先级的。一个现实的例子就是机
场登机的顺序。头等舱和商务舱乘客的优先级要高于经济舱乘客。


```js
function PriorityQueue() {
  let items = [];
  function QueueElement(element, priority) {
    // {1}
    this.element = element;
    this.priority = priority;
  }
  this.enqueue = function(element, priority) {
    let queueElement = new QueueElement(element, priority);
    let added = false;
    for (let i = 0; i < items.length; i++) {
      if (queueElement.priority < items[i].priority) {
        // {2}
        items.splice(i, 0, queueElement); // {3}
        added = true;
        break; // {4}
      }
    }
    if (!added) {
      items.push(queueElement); //{5}
    }
  };
  this.print = function() {
    for (let i = 0; i < items.length; i++) {
      console.log(`${items[i].element} -
 ${items[i].priority}`);
    }
  };
  //其他方法和默认的Queue实现相同
}
```
