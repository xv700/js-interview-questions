# js面试题

#### 介绍
群里有java朋友要面试前端，找我要面试题，我就给了这个

#### 1.基本类型 typeof

Boolean  
String  
Number  
Null  
Undefined  
Symbol（ES6 新定义）   

能答出基本类型三个以上即可  

 **扩展**   
引用数据类型：对象(Object)、数组(Array)、函数(Function)。  

#### 2.举例说说什么是闭包


```js
function f1(){
var n=999;
function f2(){
n++;
alert(n);
}
return f2;
}
　
var result=f1();
result(); // 1000
result(); // 1001
```
变量存到f1里，对外不可见，但是一直不销毁，就像面向对象的私有属性    
能说出return一个函数，给一半分

#### 3.ES6变量定义

var let const 区别  
var会出现变量提升，let，const不会  
let可改变，  
const是只读变量，但是const a={b:1}指向了一个object，object内部可变(a.b=2,是可以变的)  

#### 4.解构
```js
//两个obj,{a:1}、{b:1}合并成一个obj 

  var obj={...{a:1},...{b:1}}
console.log(obj)  //{a:1,b:1}

///////////////////////////////////

//获取a对象中b的值
var a={b:1};
var {b}=a;
console.log(b)  //1
```

#### 5.通过 CSS 选择器获取
```js
//获取页面上的所有a标签DOM对象,答出一个就行
var a1=document.getElementsByTagName('a') //
var a2=document.querySelectorAll('a') //ES5新加
////////////////////////

//获取页面上的所有a标签，并且class是abc的,ES5
 
document.querySelectorAll('a.abc')
//知道document.querySelectorAll就行
```
#### 6.变量声明var提升
```js
1行   a()
2行   var a=10
3行   function a(){console.log(a)}
4行   a()

//第一行和第四行输出什么？

//答案：
//第一行：输出function a()函数体
//第四行：报错语法错误

//因为变量声明var提升，答出这里就可以

//但是函数体提升优先级更高
```

#### 7.this指向
```js
 const obj={
        a:10,
        c:this.a,
        getA:function(){
          return this.a
        }
      }
      console.log(obj.c);  //undefined
      console.log(obj.getA());  //10
      const test = obj.getA;
      console.log(test());   //undefined

```

#### 8.函数内的this指向

```HTML
<div></div>
```