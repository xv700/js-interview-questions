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


```
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

#### 3.ES6

var let const 区别  
var会出现变量提升，let，const不会  
let可改变，  
const是只读变量，但是const a={b:1}指向了一个object，object内部可变(a.b=2,是可以变的)  

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


#### 特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)