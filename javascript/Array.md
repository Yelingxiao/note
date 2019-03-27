# Array

## 属性

### length

- 返回或设置一个数组中的元素个数。

### prototype

- 表示 Array 构造函数的原型，并允许您向所有Array对象添加新的属性和方法。

### Array.prototype[@@unscopables]

- with 绑定中未包含的数组默认属性有：copyWithin, entries, fill, find, findIndex, includes, keys 和 values。

## 构建方法

### Array.isArray(obj)

- obj需要检测的值。如果对象是 Array，则返回值为true; 否则为false。

### Array.from(arrayLike[, mapFn[, thisArg]])

- 将一个类似数组或可迭代对象中创建一个新的数组实例

### Array.of(item...)

- 创建一个具有可变数量参数的新数组实例，而不考虑参数的数量或类型

### Array(element) 

- 构造函数之间的区别在于处理整数参数

## 实例方法

### 转换方法

- arr.join([separator])
  - 所有的数组元素被转换成字符串，再用一个分隔符将这些字符串连接起来。
- arr.toString()
  - 返回一个字符串，表示指定的数组及其元素。
- arr.toLocaleString([locales[,options]])
  - 返回一个字符串表示数组中的元素。数组中的元素将使用各自的 toLocaleString 方法转成字符串，这些字符串将使用一个特定语言环境的字符串（例如一个逗号 ","）隔开

### 栈方法

- arr.push(item...)
  - 一个或多个元素添加到数组的末尾，并返回该数组的新长度。
- arr.pop()
  - 从数组中删除最后一个元素，并返回该元素的值。此方法更改数组的长度。

### 队列方法

- arr.shift()
  - 从数组中删除第一个元素，并返回该元素的值。此方法更改数组的长度。
- arr.unshift(item...)
  - 将一个或多个元素添加到数组的开头，并返回该数组的新长度。

### 重排序方法

- arr.reverse()
  - 将数组中元素的位置颠倒,并返回该数组。该方法会改变原数组。
- arr.sort([compareFunction])
  - 对数组的元素进行排序，并返回数组。排序算法现在是稳定的。

### 操作方法

- arr. concat(item,,,)
  - 合并两个或多个数组。此方法不会更改现有数组，而是返回一个新数组。
- arr.slice(start, end)
  - 返回一个新的数组对象，这一对象是一个由start和 end（不包括end）决定的原数组的浅拷贝。原始数组不会被改变。
- arr.splice(start,deleteCount,item..) 
  - 通过删除或替换现有元素来修改数组,并以数组形式返回被修改的内容。此方法会改变原数组。
- arr.copyWithin(target,start,end)
  - 浅复制数组的一部分到同一数组中的另一个位置，并返回它，而不修改其大小。
- arr.fill(value,start, end)
  - 用一个固定值填充一个数组中从起始索引到终止索引内的全部元素。不包括终止索引。

### 位置方法

- arr.indexOf(searchElement, start)
  - 返回在数组中可以找到一个给定元素的第一个索引，如果不存在，则返回-1。
- arr.lastIndexOf(searchElement, end)
  - 指定元素（也即有效的 JavaScript 值或变量）在数组中的最后一个的索引，如果不存在则返回 -1。从数组的后面向前查找
- arr.includes(searchElement,start)
  - 用来判断一个数组是否包含一个指定的值，根据情况，如果包含则返回 true，否则返回false

### 遍历方法

- arr.every(callback,thisArg)
  - 对数组的所有元素是否都通过了指定函数的测试。通过返回true,反之返回false
- arr.some(callback,thisArg)
  - 对数组的所有元素是否有一项通过了指定函数的测试。通过返回true,反之返回false
- arr.filter(callback,thisArg)
  - 创建一个新数组, 其包含通过所提供函数实现的测试的所有元素。 
- arr.forEach(callback)
  - 对数组的每个元素执行一次提供的函数。无返回值。
- arr.map(callback,thisArg)
  - 创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后返回的结果。
- arr.find(callback,thisArg)
  - 返回数组中满足提供的测试函数的第一个元素的值。否则返回 undefined。
- arr.findIndex(callback,thisArg)
  - 返回数组中满足提供的测试函数的第一个元素的索引。否则返回-1
- arr.entries()
  - 返回一个新的Array Iterator对象，该对象包含数组中每个索引的键/值对。
- arr.keys()
  - 返回一个包含数组中每个索引键的Array Iterator对象 遍历数组keys可以用 for in
- arr.values()
  - 返回一个包含数组中每个索引的值的Array Iterator对象   遍历数组keys可以用 for of

### 归并方法

- arr.reduce(callback[, initialValue])
  - 对数组中的每个元素执行一个由您提供的reducer函数(升序执行)，将其结果汇总为单个返回值。
- arr.reduceRight(callback[, initialValue])
  - 接受一个函数作为累加器（accumulator）和数组的每个值（从右到左）将其减少为单个值

### 扁平化方法

- arr.flat(depth)
  - 按照一个可指定的深度递归遍历数组，并将所有元素与遍历到的子数组中的元素合并为一个新数组返回
- arr.flatMap(callback,thisArg)
  - 可以理解成将flat和map方法结合在一起

![Array](/Users/yelingxiao/Desktop/Array.png)

[MDN Array](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array)

[Array 脑图](http://naotu.baidu.com/file/004a52d765ff3b450d05cd45d4ee9ef0)

