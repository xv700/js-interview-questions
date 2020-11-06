# js面试题

### 介绍
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

### 2.举例说说什么是闭包


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

### 3.ES6变量定义

var let const 区别  
var会出现变量提升，let，const不会  
let可改变，  
const是只读变量，但是const a={b:1}指向了一个object，object内部可变(a.b=2,是可以变的)  

### 4.解构
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

### 5.通过 CSS 选择器获取
```js
//获取页面上的所有a标签DOM对象,答出一个就行
var a1=document.getElementsByTagName('a') //
var a2=document.querySelectorAll('a') //ES5新加
////////////////////////

//获取页面上的所有a标签，并且class是abc的,ES5
 
document.querySelectorAll('a.abc')
//知道document.querySelectorAll就行
```
### 6.变量声明var提升
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

### 7.this指向
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

### 8.函数内的this指向

```HTML
<div id="ab"></div>
<script>
var abc=document.getElementById
abc("ab") //报错
</script>
```


### 9.CSS之如何自适应，不同分辨率如何处理

能说出媒体查询即可
```css
/*CSS3 @media 查询*/
@media screen and (max-width: 300px) {
    body {
        background-color:lightblue;
    }
}
```
### 10.什么是重绘和回流

重绘和回流是面试题经常考的题目，也是性能优化当中应该注意的点，下面简单介绍下。

重绘：指的是当页面中的元素不脱离文档流，而简单地进行样式的变化，比如修改颜色、背景等，浏览器重新绘制样式。

回流：指的是处于文档流中 DOM 的尺寸大小、位置或者某些属性发生变化时，导致浏览器重新渲染部分或全部文档的情况。
相比之下，回流要比重绘消耗性能开支更大。
另外，一些属性的读取也会引起回流，
比如读取某个 DOM 的高度和宽度，或者使用 getComputedStyle 方法。
在写代码的时候要避免回流和重绘。

如果不清楚概念名字，提出以下问题

两个操作
1.一个div，只改变了他的背景颜色
2.一个div,放入一个a标签

哪个速度会快些

答案：第一会快一些，因为第一属于重绘，资源消耗少
能说出自己的逻辑理解也可

### 11.选出input，name为abc的所有元素
jQuery，由于此框架使用开始减少如果不会可以忽略
$('input[name="abc"]')

请使用jQuery选出页面所有元素
$("*")

### 12.与后端交互数据用什么
AJAX、Axios、fetch
说出一个即可，可以再说说跨域

### 13.VUE
```js
var vm = new Vue({
            el: '#',
            data: [],
            methods: {
            },
            computed :{
            },
            created:{
		this.data = [1,2,3];
            },
	    mounted:{
		this.data[0]=100;
            },
         });

```
问dom上会渲染什么  
问题只要描述一个vue的data初始赋值是[]  
created周期写的是this.data = [1,2,3];  
mounted周期写的是this.data[0]=100;  

答案是[1,2,3]  
两个考点：  
1.mounted周期比created周期晚运行，所以最后运行this.data[0]=100，    
2.但是this.data[0]的索引赋值vue检测不到，所以mounted周期运行了，数据虽然改变，但是dom不渲染  