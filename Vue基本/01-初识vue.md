# 初识Vue

1. 想让Vue工作，就必须创建一个Vue实例，且要传入一个配置对象
2. root容器里的代码依然符合html规范，只不过传入了一些特殊的Vue语法
3. root容器里的代码被称为【Vue模板】
4. Vue实例和容器是一一对应的
5. 真实开发中只有一个Vue实例，并且会配合着组件一起使用
6. {{xxx}}中的xxx要写js表达式(一个表达式会产生一个值，可放任何地方)，且xxx可以自动读取到data中的所有属性
7. data中的数据改变，那么页面中用到的该数据的地方也会自动改变

解析过程：先定义Vue模板 ——>  Vue实例拿到Vue模板解析 ——> 解析完成后创建一个新的元素放回模板位置

```html
<head>
    <script src='引入Vue'></script>
</head>
<body>
    <div>
        <h1>Hello,{{name}}</h1>
    </div>
</body>
<script>
    //创建Vue实例
	new Vue({
        el:'#root'  //建立连接；el用于指定当前Vue实例为哪个容器服务；(也可以写成document.get...)
        data:{ //data中用于存储数据，供el所指定容器使用
        	name:'尚硅谷'
    	}
    })
</script>
```

