# this的指向
在运行时，谁调用就指向谁，有一下四种情况：
- 作为对象的方法调用
- 作为普通函数的调用
- 构造函数的调用
- Function.prototype.call和Function.prototype.apply的调用

## 作为对象方法的调用

当函数作为对象的方   用时,this 指向 对象

    var obj = {
        a:1,
        getA: function() {
            console.log(this.a)//1
            console.log(this === obj)//true
        }
    }
    obj.getA()//1
## 作为普通函数的调用

this总指向全局对象

    window.name = 'xiaoming'
    var myObj = {
        name: 'xiaohong'
        getName: function(){
            return this.name
        }
    }
    var getName = myObj.getName;
    console.log(getName())//xiaoming
## 作为构造函数的调用

1. 当用new调用函数时,函数总会返回一个对象,通常下,构造器里的this指向返回的这个对象
2. 如果构造器显式的返回一个object类型的对象,那么此结果最终会返回这个对象,而不是我们之前期待的 this.

例子：

    var MyClass = function(){
    this.name=''xiaoming"
        return {
            name:''xiaohong"
        }
    }
    var obj = new MyClass();
    console.log(obj.name)//xiaohong
如果构造器不显式的返回任何数据，或者返回一个非对象类型的数据，就不会造成上述情况

## Function.prototype.call和Function.prototype.apply调用

可以动态的改变传入函数的this
