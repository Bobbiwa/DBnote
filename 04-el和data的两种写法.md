# el和data的两种写法

### el第二种写法

```html
<body>
    <div id="root">
        hello,{{name}}
    </div>
</body>
<script>
    const v = new Vue({
        // el: '#root',
        data:{
            name:'尚硅谷'
        }
    })
    setTimeout(() => {
        v.$mount('#root')  //这样与模板产生连接的写法更加灵活
    },1000)
</script>
```

### data第二种写法

```html
<body>
    <div id="root">
        hello,{{name}}
    </div>
</body>
<script>
    new Vue({
        el:'#root',
        data:function(){   //注意：(t)这里的data是底层Vue调用的，不可以写成箭头函数
            return {name:'尚硅谷'}
        }
        /*
        一般我们在对象里写函数会简写：
        data(){
            return {name:'尚硅谷'}
        }
        直接写函数，不写属性值
        */
    })
</script>
```



