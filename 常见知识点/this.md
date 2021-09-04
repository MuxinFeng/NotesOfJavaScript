## this
### this优先级
&emsp;this是关键字，指向一个对象，this指向哪个对象是由函数在作用域链的位置决定（引：this永远指向最后调用它的那个对象）。
1. 箭头函数<br>
&emsp;箭头函数没有自己的this，它的this指向自作用域链的下一个对象，并且在定义时就决定好了，无法再更改。
```
实例不正确
let apple = 1;
fruit = () =>{
    console.log(this.apple);//apple
}
fruit();
```
2. new<br>
&emsp;指向新的对象； 
3. bind<br>
&emsp;bind是将this绑定到指定的对象，bind函数的第一个参数即为this指向的对象；多个bind同时使用时，bind只会指向第一个绑定的对象。
```
let person1 = {
    name:'Jack',
};
let person2 = {
    name:'Rose',
};
let Name = {
    name:'TanTnic',
    getName:function (){
        console.log(this.name);
    }
};

Name.getName();//TanTnic
Name.getName.bind(person1);//'Jack';
Name.getName.bind(person1).bind(person2);//'Jack';
```
4. apply、call


从简单的定义开始，一步步剖析，看总结出的规律是否可以用到所有情况，不断举例，不断论证


### 参考文档
[MDN官方文档](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/this)<br/>
[嗨，你真的懂this吗？](https://juejin.cn/post/6844903805587619854)<br/>
[从这两套题，重新认识JS的this、作用域、闭包、对象](https://segmentfault.com/a/1190000010981003)<br/>
[this、apply、call、bind](https://juejin.cn/post/6844903496253177863)<br/>
[JavaScript-作用域、块级作用域、上下文、执行上下文、作用域链](https://segmentfault.com/a/1190000014876534)<br/>
[JS 中 this 指向问题](https://juejin.cn/post/6946021671656488991#heading-2)<br/>

