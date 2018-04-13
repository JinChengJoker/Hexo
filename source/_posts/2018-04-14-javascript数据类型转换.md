---
title: JavaScript数据类型转换
date: 2018-04-14 00:27:05
---

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