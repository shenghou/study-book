不能通过引用来更改引用参数的指向，只能更改引用和参数共同指向的值

```js
function foo(x) {
  x.push(4); //x  [1,2,3,4]
  x = [4, 5, 6];
  x.push(7); //x  [4,5,6,7]
}
var a = [1, 2, 3];
foo(a);
//a [1,2,3,4]
```

```js
function foo(x) {
  x.push(4); //x  [1,2,3,4]
  x.length = 0;
  x.push(4, 5, 6, 7); //x  [4,5,6,7]
}
var a = [1, 2, 3];
foo(a);
//a [4,5,6,7]
```

# `x.length = 0`并没有创建一个新的数组，而是更改当前数组，于是`a`的值变成`[4,5,6,7]`

标量为基本类型是不可更改的，如果一个数字对象的标量基本类型是 2，那么该值就不可更改，除非创建一个包含新值的数字对象

```js
function foo(x) {
  x = x + 1;
}
var a = 2;
var b = Numebr(a); //Object(a)也一样
foo(b);
//b   2
```
