第六章：移动端rem布局原理解析

![](C:\Users\25971\Desktop\移动端适配\课程.png)

1. rem是相对单位，相对于它的父级元素进行缩放，假设你现在的父级元素为20px;那么你的子元素的宽度2em就是40px；那么你的自己元素的边框2em就为80px;

2. rem是相对于根元素的：rem : root + em

3. rem原理：我们根据不同的手机宽度，更改html根元素的大小，即可完成等比例缩放，这也是移动端rem布局的原理。    我们只需要对html里面的font-size进行动态的修改就可以了。

4. JS动态计算、Flexible.js库、利用vw动态换算（推荐使用）

5. 等比例缩放公式：100vw : 375px =  ? : 100px      ?=100/375*100       ?  =    26.6666666666

   ![](C:\Users\25971\Desktop\移动端适配\px换算rem单位.png)



#### 采用等比例缩放注意的点：

如果子元素写了文字，那么文字大小将会继承根元素font-size 的大小，变得异常的大，如何解决呢？

很简单，我们只需要在body元素中呢初始化一下我们文字的大小就好了。

```css
body { font-size:16px }
```

#### 第一种方案：测量rem数值及插件（px to rem），**缺点**需要（计算所有元素除以2）

![](C:\Users\25971\Desktop\移动端适配\px-to-rem插件配置.png)

#### 在通过px to rem插件转换的时候需要注意的点：

alt + z ：转换成rem；

逻辑像素：css中设置的数值大小

物理像素：手机实际大小

而实际上物理像素是逻辑像素的2倍，所以我们在转换完逻辑像素之后呢，还需要除以2。

ps中量取的是数值，是物理像素；css中设置的是逻辑像素，所以对应的值进行除以2。

#### 第二种方案：通过pxCook进行设置：

![](C:\Users\25971\Desktop\移动端适配\pxCoook的配置.png)

#### 实战开发准备工作：

重置样式文件、icon图标文件夹、logo、psd源文件(由UI设计师提供)

#### png拉辅助线的注意点：（首先拉一条中心辅助线）

![](C:\Users\25971\Desktop\移动端适配\导航一个块儿的代销.png)

#### 多行多列的布局注意点：（块儿高度的测量）

![](C:\Users\25971\Desktop\移动端适配\高度测量.png)

#### 开启网格布局

```css
.nav-sub-list{
    display: grid;
    grid-template-columns: repeats(5 , 1fr);   // 五列
    grid-auto-rows: 35px;
}

当一个 HTML 元素将 display 属性设置为 grid 或 inline-grid 后，它就变成了一个网格容器，这个元素的所有直系子元素将成为网格元素。
.grid-container {
  display: grid;	// 开启网格布局
}

.grid-container {
  display: inline-grid;
}

网格轨道
我们通过 grid-template-columns 和 grid-template-rows 属性来定义网格中的行和列。
这些属性定义了网格的轨道，一个网格轨道就是网格中任意两条线之间的空间。
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto auto;
}

我们使用 grid-template-rows 属性在网格容器中设置行的高度:
.grid-container {
  display: grid;
  grid-template-rows: 100px 300px;
}

fr 单位
轨道可以使用任何长度单位进行定义。
网格引入了 fr 单位来帮助我们创建灵活的网格轨道。一个 fr 单位代表网格容器中可用空间的一等份。
.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
```

网格布局菜鸟教程：https://www.runoob.com/css3/css-grid.html

- grid-column-gap
- grid-row-gap
- grid-gap

![](C:\Users\25971\Desktop\移动端适配\cloumn.png)

![](C:\Users\25971\Desktop\移动端适配\row.png)

![](C:\Users\25971\Desktop\移动端适配\间距.png)

#### 图片等比例缩放属性：

![](C:\Users\25971\Desktop\移动端适配\图片等比例缩放.png)

#### 不让文字收缩：（哔哩哔哩导航）

![](C:\Users\25971\Desktop\移动端适配\不让文字收缩.png)

#### grid布局：多行多列

![](C:\Users\25971\Desktop\移动端适配\grid布局.png)

#### 网易布局、B站vw布局：掌握弹性盒布局、grid布局、适配





