1. Promise是抽象的异步处理对象以及对其进行各种操作的组件。
2. 以前基于js的异步处理，一般都是使用回调函数，现在我也是这样的。
3. Node.js等则规定在JavaScript的回调函数的第一个参数为 Error 对象，这也是它的一个惯例。但是这仅仅是个规范，你想怎么写就怎么写。
而Promise则是把类似的异步处理对象和处理规则进行规范化， 并按照采用统一的接口来编写，除promise对象规定的方法(这里的 then 或 catch)以外的方法都是不可以使用的，
而不会像回调函数方式那样可以自己自由的定义回调函数的参数，而必须严格遵守固定、统一的编程方式来编写代码
4. promise的功能是可以将复杂的异步处理轻松地进行模式化
5.  - 用 new Promise 方法创建promise对象
    - 用.then 或 .catch 添加promise对象的处理函数
6. Promise.resolve，可以认为它的作用就是将传递给它的参数填充（Fulfilled）到promise对象后并返回这个promise对象。
7. 使用promise.then(onFulfilled, onRejected) 的话
   在 onFulfilled 中发生异常的话，在 onRejected 中是捕获不到这个异常的。
   在 promise.then(onFulfilled).catch(onRejected) 的情况下
   then 中产生的异常能在 .catch 中捕获
   .then 和 .catch 在本质上是没有区别的
