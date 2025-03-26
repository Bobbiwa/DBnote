### 一、Flex布局概念

Flexbox布局也叫Flex布局，弹性盒子布局。它的**目标**是提供一个更有效地布局、对齐方式，并且能够使父元素在子元素的大小未知或动态变化情况下仍然能够分配好子元素之间的间隙。**主要思想**是使父元素能够调整子元素的宽度、高度、排列方式，从而更好的适应可用的布局空间。设定为flex布局的元素能够放大子元素使之尽可能填充可用空间，也可以收缩子元素使之不溢出。 

Flex布局更适合小规模的布局，可以简便、完整、响应式的实现各种页面布局。但是，设为Flex布局以后，其子元素的`float`、`clear`和`vertical-align`属性将失效。Flex弹性盒模型的优势在于只需声明布局应该具有的⾏为，⽽不需要给出具体的实现⽅式，浏览器负责完成实际布局，当布局涉及到不定宽度，分布对⻬的场景时，就要优先考虑弹性盒布局。

Flex布局是一个完整的模块，它包括了一套完整的属性。其中采用 Flex 布局的元素，称为 Flex 容器，简称"**容器**"。它的所有子元素就是容器成员，称为 Flex 项目，简称"**项目**"。![Flexbox布局.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bb462fbbab1f4dfca38b871571af7091~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

容器默认存在两个轴：**主轴（main axis）**和 **交叉轴（cross axis）**，项目始终沿主轴排列：

![Flexbox布局-主轴.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bbbad88b6c9d4a22a82da2e5f0c21f0c~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

这里面涉及到了几个概念，下面来看一下：

- **main axis**: Flex 父元素的主轴是指子元素布局的主要方向轴，它由属性flex-direction来确定主轴是水平还是垂直的，默认为水平轴。
- **main-start & main-end**: 分别表示主轴的开始和结束，子元素在父元素中会沿着主轴从main-start到main-end排布。
- **main size**: 单个项目占据主轴的长度大小。
- **cross axis**: 交叉轴，与主轴垂直。
- **cross-start & cross-end**: 分别表示交叉轴的开始和结束。子元素在交叉轴的排布从cross-start开始到cross-end。
- **cross size**: 子元素在交叉轴方向上的大小。

### 二、父元素属性

父元素（容器）可以设置以下六个属性：

- flex-direction
- flex-wrap
- flex-flow
- justify-content
- align-items
- align-content

##### flex-direction

> 决定了主轴的方向(水平/垂直)，以及项目排列方向

1. `flex-direction: row`：默认值，主轴沿 **行向** 延伸，项目从左到右排列，起点在左沿

![Flexbox布局-flex-direction.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/b8122d1fc3014d9db734ca6ad6bd189f~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

2. `flex-direction: row-reverse`：主轴沿 **行向**  延伸 ，项目从右到左排列，起点在右沿

   ![Flexbox布局-flex-direction1.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7207fba6595248cea381f972a45669a1~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

3. `flex-direction: column`：主轴沿 **纵向** 延伸，项目从上到下排列，起点在上沿

![Flexbox布局-flex-direction2.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/06998644245049dcbd7b5dc4b2841a73~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

4. `flex-direction: column-reverse`：主轴沿 **纵向** 延伸，项目从下到上排列，起点在下沿

![Flexbox布局-flex-direction4.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2e081dde5cf248c781fcf03ae383fea3~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

##### flex-wrap

> 容器内元素是否可以换行

1. `flex-wrap: nowrap`：默认值，不换行。子元素挤在一行，宽度不足时被压缩（根据 `flex-shrink`）或溢出容器。

https://juejin.cn/post/7004622232378966046

### 三、子元素属性
