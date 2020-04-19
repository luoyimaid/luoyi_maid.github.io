---
title: 原生JS实现常见高阶数组方法
date: 2020-04-02 17:40:23
tags: 原生JS
---

- 在实现之前，我们先来介绍一下高阶函数：可以接收另外一个函数作为参数或者返回值的函数
- 那么高阶数组方法也是高阶函数

### 1. 实现一个map方法

- map：接收两个参数，一个是回调函数，一个是this（可选）, 并且对原数组没有影响
- 可以先捋一下实现思路
    1. 首先肯定是将map方法挂在数组原型上，并且接收两个参数，如上所说
    2. 先对this，callback做容错处理，严谨一点
    3. 将参数强转为对象
    4. 创建一个新的数组，不用改变原数组
    5. for...in...循环遍历

```
Array.prototype.map = function(callbackFn, thisArg) {
    // 处理this异常
    if(this === null || this === undefined) {
        throw new TypeError("Cannot read property 'map' of null or undefined");
    }
    if(Object.prototype.toString.call(callbackFn) !== '[object Function]') {
        throw new TypeError("callbackFn is not a function");
    }

    let o = Object(this);
    let t = thisArg;

    let length = o.length >>> 0;
    let array = new Array(length);

    for(let k = 0; k < length; k++) {
        if(k in o) {
            let value = o[k];
            // 依次传入this, 当前项，索引，整个数组
            let mappedValue = callbackFn.call(t, value, k, o);
            array[k] = mappedValue;
        }
    }
    return array;
};

let arrayq = [1, 2, 3, 4, 5];
let newArray = arrayq.map((item, index) => {
    console.log(item, index);
    return item * index;
});

console.log(newArray);
// 1 0
// 2 1
// 3 2
// 4 3
// 5 4
// [0, 2, 6, 12, 20]
```

### 2. 实现一个reduce方法

- reduce：接收两个参数，一个是回调函数，一个是初始值（可选）, 并且对原数组没有影响
- 可以先捋一下实现思路
    1. 首先肯定是将map方法挂在数组原型上，并且接收两个参数，如上所说
    2. 先对this，callback做容错处理，严谨一点
    3. 将参数强转为对象
    4. 初始化兼容，如果没有传初始值，默认选数组第一项作为初始值
    5. for...in...循环遍历数组，实现累加
```
Array.prototype.reduce = function(callbackFn, currentValue) {
    // 处理this异常
    if(this === null || this === undefined) {
        throw new TypeError("Cannot read property 'map' of null or undefined");
    }
    // 处理回调异常
    if(Object.prototype.toString.call(callbackFn) !== '[object Function]') {
        throw new TypeError("`${callbackFn}` is not a function");
    }
    let o = Object(this);
    let accumulator = currentValue;
    let k = 0;
    if(accumulator === undefined) {
        for(; k < o.length; k++) {
            // 查找原型链
            if(k in o) {
                accumulator = o[k];
                k++;
                break;
            }
            // 数组循环完还没有出逻辑，说明数组是空数组
            throw new Error('empty array');
        }
    }
    for(; k < o.length; k++) {
        if(k in o) {
            accumulator = callbackFn.call(undefined, accumulator, o[k], k, o);
        }
    }
    return accumulator;
}
let array = [1, 2, 3, 4, 5];
let reduceArray = array.reduce((preNum, curNum) => {
    return preNum + curNum;
});
console.log(reduceArray);
// 15
```

### 3. 实现一个filter方法

- filter: filter返回一个新的数组，数组里包含参数里所有被保留的项
- 这个方法只接收一个参数，就是数组的当前项,回调函数返回一个布尔类型，来决定当前参数的去留
```
Array.prototype.filter = function(callbackFn, thisArg) {
    // 处理this异常
    if(this === null || this === undefined) {
        throw new TypeError("Cannot read property 'map' of null or undefined");
    }
    // 处理回调异常
    if(Object.prototype.toString.call(callbackFn) !== '[object Function]') {
        throw new TypeError("`${callbackFn}` is not a function");
    }
    let o = Object(this);

    // 新数组
    let length = 0;
    let array = [];
    for(let i = 0; i < o.length; i++) {
        if(i in o) {
            if(callbackFn.call(thisArg, o[i], i, o)) {
                array[length++] = o[i];
            }
        }
    }
    return array;
}
let array = [1, 2, 3, 4, 5];
let filterArray = array.filter(item => item % 2);
console.log(filterArray);
// [1, 3, 5]
```