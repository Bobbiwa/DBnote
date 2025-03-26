# 回顾Object.definedProerty

### 直接设置属性和Object.defineProperty设置属性的区别



```javascript
let person = {
    name:"张三",
    sex:"男"
    //age:18    如果直接写上去，那么默认都可枚举、修改、删除
}
Object.defineProperty(person,'age',{
    value:18,
    enumerable:true,    //可枚举？   默认false
    writable:true,      //可修改？    默认false
    configurable:true,  //可删除？    默认false
})
```

### Object.definedProperty配置对象中的get方法和set方法



场景：当我们想把`属性值`通过变量number的形式设置在对象外面，当我们修改这个number时，对象内部的age不会改变，这是因为person对象只会读取一遍，只会在建立初期第一次时访问number，之后就一直固定。

```javascript
let number = 18
let person = {
    name:"张三",
    sex:"男",
    age:number
}
console.log(person.age) //18
number = 19
console.log(person.age) //18

```

为了想通过改变number来影响person属性值的改变，可以利用以下方式：

```javascript
let number = 18

let person = {
    name:"张三",
    sex:"男"   
}
Object.defineProperty(person,'age',{
    value:18,
    //当有人读取person的age属性时，get函数(getter)就会被调用，且返回值就是age的值
    get(){
        console.log('有人读取了age属性')
        return number
    }
    
    //当有人修改了person的age属性时，set函数(setter)就会被调用，且会收到修改的具体值
    set(value){
    	console.log('有人修改里age属性,且值是value')
    	//注意：调用了这个函数并非会直接修改值，而是需要手动修改number才行
    	number = value
	}
})
```





