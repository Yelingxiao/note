# Object

## 属性

### Object.prototype

- 可以为所有 Object 类型的对象添加属性。

### Object.prototype.constructor

- 所有对象都会从它的原型上继承一个 constructor

## 方法

### Object.assign()

- 将所有可枚举属性的值从一个或多个源对象复制到目标对象。它将返回目标对象。

### Object.create()

- 使用指定的原型对象和属性创建一个新对象。

### Object.defineProperty()

- 给对象添加一个属性并指定该属性的配置。

### Object.defineProperties()

- 给对象添加多个属性并分别指定它们的配置。

### Object.freeze()

- 冻结对象：其他代码不能删除或更改任何属性。

### Object.isFrozen()

- 判断对象是否已经冻结。

### Object.seal()

- 密封一个对象，阻止添加新属性并将所有现有属性标记为不可配置。当前属性的值只要可写就可以改变。

### Object.isSealed()

- 判断一个对象是否被密封。

### Object.preventExtensions()

- 让一个对象变的不可扩展，也就是永远不能再添加新的属性。

### Object.isExtensible()

- 判断一个对象是否是可扩展的（是否可以在它上面添加新的属性）。

### Object.is()

- 比较两个值是否相同。所有 NaN 值都相等（这与==和===不同）

### Object.keys()

- 返回一个包含所有给定对象自身可枚举属性名称的数组。

### Object.values()

- 返回给定对象自身可枚举值的数组。

### Object.entries()

- 返回给定对象自身可枚举属性的[key, value]数组。

### Object.getOwnPropertyDescriptor()

- 返回指定对象上一个自有属性对应的属性描述符。

### Object.getOwnPropertyNames()

- 返回一个数组，它包含了指定对象所有的可枚举或不可枚举的属性名。

### Object.getOwnPropertySymbols()

- 返回一个给定对象自身的所有 Symbol 属性的数组。

### Object.setPrototypeOf()

- 设置一个指定的对象的原型 ( 即, 内部[[Prototype]]属性）到另一个对象或  null
。

## 实例方法

### obj.hasOwnProperty()

- 返回一个布尔值，指示对象自身属性中是否具有指定的属性

### obj. isPrototypeOf()

- 测试一个对象是否存在于另一个对象的原型链上。

### obj.propertyIsEnumerable()

- 返回一个布尔值，表示指定的属性是否可枚举。

### obj.toLocaleString()

- 返回一个该对象的字符串表示。

### obj.tostring()

- 返回一个表示该对象的字符串。



[MDN Object](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object)

[Object 思维导图](http://naotu.baidu.com/file/72792727901efc95ffc0829452820dcc)

