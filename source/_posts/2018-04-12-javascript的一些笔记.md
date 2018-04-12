---
title: JavaScript的一些笔记
date: 2018-04-12 22:44:04
---

### 基本类型

Number、String、Boolean、Symbol、null、undefined

### 复杂类型

Object - 复杂类型由基本类型组成

### Number

| 进制 | 说明 | 示例 |
| :-: | :-:| :-: |
| 十进制 | - | 123 |
| 十进制 | 浮点数 | 1.23 |
| 十进制 | 科学计数 | 1.23e2 = 123 |
| 二进制 | 以 0b 开头 | 0b11 |
| 八进制 | 以 0 开头 | 011 |
| 十六进制 | 以 0x 开头 | 0x11 |

### null 和 undefined

- 如果一个变量没有赋值，那么它就是 undefined。
- 惯例 - 如果要声明一个对象，且暂时没有值，可以初始化为 null。
- 惯例 - 如果要声明一个非对象，且暂时没有值，可以初始化为 undefined。

### Object

- object 的 key 只能是字符串，但有些情况可以省略引号。
- 声明 `key` 时，如果不加引号，则 `key` 必须以标识符（变量名）的规定命名；如果加引号，则没有这样的限制。
    ```
    var obj = { 9name: 'joker' }  // 报错
    obj[9name] = 'joker'  // 报错
    var obj = { '9name': 'joker' }  // 正确
    var obj = { '9 name': 'joker' } // 正确
    ```
- 用 `obj['key']` 取值时，必须加上引号，否则 `key` 就是变量。
- 当 key 符合标识符（变量名）规定时，可以用 `object.key` 取值。
- `key in object` 用于判断一个属性是否存在于 object 中，如果存在就返回true，否则返回false。
    ```
    var obj = { p: 1 }
    'p' in obj // true
    ```
- `for...in` 用于遍历 object 的属性。
    ```
    var obj = { a: 1, b: 2, c: 3 }
    for(var key in obj) {
        console.log(key)
    }
    // 'a'
    // 'b'
    // 'c'
    for(var key in obj) {
        console.log(obj[key])  // 注意这里 typeof key 为 string
    }
    // 1
    // 2
    // 3
    ```
- `Object.keys()` 可以查看一个对象的所有属性。
    ```
    var obj = { a: 1, b: 2, c: 3 }
    Object.keys(obj)  // ['a', 'b', 'c']
    ```
- `delete obj.key` 用于删除 object 中的属性，删除成功后返回 true。
    ```
    var obj = { p: 1 }
    delete obj.p  // true
    obj.p  // undefined
    ```