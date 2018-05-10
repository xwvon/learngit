# 有关this、call、apply的记录
## 1. this的指向
+ 作为对象的方法调用，this指向该对象
```js
const obj = {
    a: 1,
    getA: function () {
        alert(this.a); //1
        alert(this === obj); //true
    }
}
```
+ 作为普通函数调用，this指向全局对象，即`window`

```js
function func() {
    alert(this === window);
}
func(); //true
```
```js
window.name = 'zyxw_feng';
const myObj = {
    name: 'objName',
    getName: function () {
        return this.name;
    }
};
const getName = myObj.getName;
myObj.getName(); //objName
getName(); //zyxw_feng
```
在div节点的事件函数内部，有一个局部的callback方法，callback作为普通函数调用的时候，callback内部的this指向了window
```js
document.getElementById('div1').onclick = function () {
    alert(this.id); //div1
    const callback = function () {
        alert(this.id); //undefined
    }
    callback();
}
```
解决上面问题的一个简单方法是将this保存起来
```js
document.getElementById('div1').onclick = function () {
    alert(this.id); //div1
    const that = this;
    const callback = function () {
        alert(that.id); //div1
    }
    callback();
};
```

+ 在构造函数里调用时，this指向返回的这个新对象
```js
function My() {
    this.name = 'zyxw_feng';
}
const obj = new My();
console.log(obj.name); //zyxw_feng
```
+ Function.prototype.call和Function.prototype.apply  
>call动态改变this的指向
```js
const obj0 = {
    name: 'zyxw_feng',
    getName: function () {
        return this.name;
    }
};
const obj1 = {
    name: 'Michael'
};
obj0.getName(); //zyxw_feng
obj0.getName.call(obj1); //Michael
```
## 2. call和apply的区别
Function.prototype.call和Function.prototype.apply方法的的作用的方法一样，区别在于它们的传参方式
+ apply接受两个可选参数，第一个可选参数指定函数this的指向对象，第二个参数是一个数组或类数组对象，这个数组的元素就是函数的参数
```js
const func = function (arg1, arg2) {

}
func.apply(this, [arg1, arg2]);
```
+ call接受多个可选参数，第一个可选参数和apply一样，是你要指定的上下文，剩下的参数按顺序传递给函数
```js
func.call(this, arg1, arg2);
```