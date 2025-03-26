# 理解MVVM

MVVM模型：

1. M：模型（Model）：data中的数据
2. V：视图（View）：模板代码
3. VM：视图模型（ViewModel）：Vue实例

<img src="C:\Users\DB\AppData\Roaming\Typora\typora-user-images\image-20220430161715060.png" alt="image-20220430161715060" style="zoom:80%;" />

观察发现：

1. data中所有的属性，最后都会放在vm身上
2. vm身上所有的属性及Vue原型上的所有熟悉，在{{}}模板中都可以访问

```html
<body>
    <div id="root">
        <h1>你好：{{name}}</h1>
        <h1>测试1：{{$emit}}</h1>  /*模板中可以访问vm身上所有属性*/
        <h1>测试2：{{$options}}</h1>
    </div>
</body>
<script>
    const vm = new Vue({
        el:'#root',
        data:{name:'尚硅谷'}  // 将name:'尚硅谷'作为属性放到vm身上
    })
</script>
```

<font color=red>注意：模板里可以直接查找vm身上的属性</font>
