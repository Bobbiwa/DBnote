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

![Flexbox布局-flex-direction3.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/932be94ebfc7406ebc0cca4081d56d01~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

2. `flex-wrap: wrap`：换行，第一行在上面

![Flexbox布局-flex-direction5.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1b105359b1fe4eaeb8a7dafc28758ca7~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

3. `flex-wrap: wrap-reverse`：换行，第一行在下面
   ![Flexbox布局-flex-direction6.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9aed6721089d4946833f366eba4ef805~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

##### flex-flow

> `flex-flow` 是 `flex-direction` 属性和`flex-wrap`属性的简写，默认为:`flex-flow:row nowrap`

##### justify-content

> 元素在主轴的对齐方式

1. `justify-content : flex-start`：默认值，元素在**主轴**的**起点**对齐
   ![Flexbox布局-jusitify.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/dc3cb0302c0b40c292be4209b7343322~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)
2. `justify-content : flex-end`：元素在**主轴**的**终点**对齐
   ![Flexbox布局-flex1.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a51c9d5bfa0e4d8a92eee2b72c92a9f9~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

3. `justify-content : center` ：元素在主轴上**居中对齐**
   ![Flexbox布局-flex3png.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/19563cdfc6e54dd8b20eb7abfe974bee~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

4. `justify-content : space-between`：元素在主轴上**两端对齐**，元素之间间隔相等

![Flexbox布局-flex4.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d079efda3a8c4991b3f717f03c19d9e7~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

5. `justify-content : space-around` ：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。

![Flexbox布局-flex5.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/395b8a44128740c8835917b9493bca95~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

##### align-items

> 元素在交叉轴上的对齐方式 (单轴)

1. `align-item：flex-start`：交叉轴的起点对齐。

![Flexbox布局-flex2.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6165710dff03433c85e0fadf320a02c6~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

2. `align-item：flex-end`：交叉轴的终点对齐。
   ![Flexbox布局-flex3.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8f483478ed3144d29d882ada2cf86fb3~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

3. `align-item：center`：交叉轴的中点对齐。

![Flexbox布局-flex4.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/083aa675e8d44835b998ef78fa45b5a9~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

4. `align-item：stretch`：(默认值) 如果元素未设置高度或设为auto，将占满整个容器的高度。

![Flexbox布局-flex1.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/78907bb8c6d64be8abd2053de12b32de~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

5. `align-item：baseline`：以元素的第一行文字的基线对齐（字母的底部对齐在这条线上）

![Flexbox布局-flex5.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8858b3521f704d0287750a5f4fbaa722~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

##### align-content

> 元素在交叉轴上的对齐方式 (多轴)。**如果容器只有一根轴线，该属性不起作**用。

那这个轴线数怎么确定呢？实际上这主要是由flex-wrap属性决定的，当flex-wrap 设置为 nowrap 时，容器仅存在一根轴线，因为项目不会换行，就不会产生多条轴线。当 flex-wrap 设置为 wrap 时，容器可能会出现多条轴线，这时就需要去设置多条轴线之间的对齐方式。

1. `align-content: stretch`：默认值，当 Flex 容器存在 **多根交叉轴线（多行或多列）** 时，该属性值会将每根轴线（行或列）拉伸，以 **均分容器在交叉轴方向的剩余空间**
   ![Flexbox布局-flex-10.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/455fa2e5821c4465adbc209fd5ea12c7~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

下面就去掉每个项目的高度，它会占满整个交叉轴，效果如下：

![Flexbox布局-flex11.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/88222e483e654d69ac70444e890744e7~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp)

##### align-items 和align-content对比

| **属性**     | `align-items: stretch`                                       | `align-content: stretch`             |
| :----------- | :----------------------------------------------------------- | :----------------------------------- |
| **作用范围** | 单行/列内的每个项目                                          | 多行/列的整体分布                    |
| **生效条件** | 始终生效（无论是否换行）                                     | 需满足换行且存在多行/列              |
| **拉伸目标** | (如果项目没有高/宽度或设置auto)项目自身<br />填满交叉轴方向空间 | 多行/列均分容器剩余空间，每行/列拉伸 |
| **典型场景** | 统一单行内项目的高度/宽度                                    | 多行/列均匀填满容器（如瀑布流布局）  |

### 三、子元素属性
