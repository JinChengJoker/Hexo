---
title: JavaScript数据类型转换
date: 2018-04-14 00:27:05
---

写着写着就不敢往下继续写了...各种奇怪的值。

## 转换为 string

### toString() 方法

- boolean
    ```
    true.toString()  // "true"
    false.toString()  // "false"
    ```

- null 没有 `toString()` 方法
    ```
    null.toString()  // 报错
    ```

- undefined 没有 `toString()` 方法
    ```
    undefined.toString()  // 报错
    ```

- object `toString()` 结果都是 `"[object Object]"`
    ```
    var obj = {}
    obj.toString()  // "[object Object]"
    
    var obj = {a: 'hello'}
    obj.toString()  // "[object Object]"
    ```

- array
    ```
    var arr = []
    arr.toString()  // ""
    
    var arr = ['a', 'b']
    arr.toString()  // "a,b"
    
    var arr = ['a', 'b', { c: 'hello' }]
    arr.toString()  // "a,b,[object Object]"
    ```
    
- function
    ```
    var func = function(key) {console.log(key)}
    func.toString()  // "function (key) {console.log(key)}" function 和括号之间有空格
    
    function zzz(key) {console.log(key)}
    zzz.toString()  // "function zzz(key) {console.log(key)}"
    ```

### 加空字符串方法

- boolean
    ```
    true + ''  // "true"
    false + ''  // "false"
    ```

- null
    ```
    null + ''  // "null"
    ```

- undefined
    ```
    undefined + ''  // "undefined"
    ```

- object
    ```
    var obj = {}
    obj + ''  // "[object Object]"
    
    var obj = {a: 'hello'}
    obj + ''  // "[object Object]"
    ```

- array
    ```
    var arr = []
    arr + ''  // ""
    
    var arr = ['a', 'b']
    arr + ''  // "a,b"
    
    var arr = ['a', 'b', { c: 'hello' }]
    arr + ''  // "a,b,[object Object]"
    ```
    
- function
    ```
    var func = function(key) {console.log(key)}
    func + ''  // "function (key) {console.log(key)}" function 和括号之间有空格
    
    function zzz(key) {console.log(key)}
    zzz + ''  // "function zzz(key) {console.log(key)}"
    ```

### 全局方法 String()

*结果与加空字符串方法一致*

## 转换为 Boolean

### 全局方法 Boolean()

- number
    ```
    Boolean(0)  // false
    Boolean(NaN)  // false
    
    Boolean(1)  // true
    Boolean(-1)  // true
    Boolean(1.23)  // true
    ```

- string
    ```
    // 空字符串
    Boolean('')  // false
    
    // 非空字符串
    Boolean(' ')  // true
    ```

- null 和 undefined
    ```
    Boolean(null)  // false
    Boolean(undefined)  // false
    ```

- object
    ```
    // 空对象
    Boolean({})  // true
    
    // 非空对象
    var obj = {a: 'hello'}
    Boolean(obj)  // true
    
    // 空数组
    Boolean([])  // true
    
    // 非空数组
    var arr = ['a', 'b']
    Boolean(arr)  // true
    
    function fn(key) {
        console.log(key)
    }
    Boolean(fn) // true
    ```

### 两次取反法 !!

*结果与全局方法 `Boolean()` 一致*

- number
    ```
    !! 0  // false
    !! NaN  // false
    
    !! 1  // true
    !! -1  // true
    !! 1.23  // true
    ```

- string
    ```
    // 空字符串
    !! ''  // false
    
    // 非空字符串
    !! ' '  // true
    ```

- null 和 undefined
    ```
    !! null  // false
    !! undefined  // false
    ```

- object
    ```
    // 空对象
    !! {}  // true
    
    // 非空对象
    var obj = {a: 'hello'}
    !! obj  // true
    
    // 空数组
    !! []  // true
    
    // 非空数组
    var arr = ['a', 'b']
    !! arr  // true
    
    function fn(key) {
        console.log(key)
    }
    !! fn  // true
    ```

## 转换为 Number

### 全局方法 Number()

- string
    ```
    Number('1')  // 1
    Number('-1')  // -1
    Number('1.23')  // 1.23
    
    // 空字符串
    Number('')  // 0
    
    // 空格字符串
    Number(' ')  // 0
    
    // 非空字符串
    Number('abc')  // NaN
    ```

- boolean
    ```
    Number(true)  // 1
    Number(false)  // 0
    ```

- null 和 undefined
    ```
    Number(null)  // 0
    Number(undefined)  // NaN
    ```

- object
    ```
    // 空对象
    var obj = {}
    Number(obj)  // NaN
    
    // 非空对象
    var obj = {a: 'hello'}
    Number(obj)  // NaN
    
    // 空数组
    Number([])  // 0
    
    // 非空数组
    var arr = ['a', '6']
    Number(arr)  // NaN
    
    // 非空数组且只有一个元素是数值
    var arr = ['6']
    Number(arr)  // 6
    
    function fn(key) {
        console.log(key)
    }
    Number(fn) // NaN
    ```

### 减去 0 方法

*结果与全局方法 `Number()` 一致*

- string
    ```
    '1' - 0  // 1
    '-1' - 0  // -1
    '1.23' - 0  // 1.23
    
    // 空字符串
    '' - 0  // 0
    
    // 空格字符串
    ' ' - 0  // 0
    
    // 非空字符串
    'abc' - 0  // NaN
    ```

- boolean
    ```
    true - 0  // 1
    false - 0  // 0
    ```

- null 和 undefined
    ```
    null - 0  // 0
    undefined - 0  // NaN
    ```

- object
    ```
    // 空对象
    var obj = {}
    obj - 0  // NaN
    
    // 非空对象
    var obj = {a: 'hello'}
    obj - 0  // NaN
    
    // 空数组
    [] - 0  // 0
    
    // 非空数组
    var arr = ['a', '6']
    arr - 0  // NaN
    
    // 非空数组且只有一个元素是数值
    var arr = ['6']
    arr - 0  // 6
    
    function fn(key) {
        console.log(key)
    }
    fn - 0 // NaN
    ```