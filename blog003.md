# CSS 知识总结

![hello](./hello.png)

## 目录

1. 简介
2. 选择器
3. 文档流与盒模型
4. 布局
5. CSS 定位
6. CSS 动画

## 简介

CSS 的全称为 Cascading Style Sheets，1994 年由李爵士的挪威同事赖先生提出。目前最广泛的应用版本为 CSS2.1。最新的 CSS3 在推行模块化。

## 选择器

-   元素选择器；
    1. ID 选择器: "#+ID 名"；
    2. 类选择器: ".+类名"；
    3. 通用选择器: "\*" 选中所有元素；
    4. 属性选择器: 用[ ]将属性包起来；
-   组合选择器:
    1. A,B:同时选中 A 和 B；
    2. A B:选中 A 的后代 B；
    3. A>B:选中 A 的直接子元素 B；
    4. A+B:选中 A 的下一个相邻元素；
    5. A~B:选中 A 后的 N 个相邻元素；
    6. AB:选中同时满足 A 和 B 的元素。

## 文档流与盒模型

-   文档流(Normal Flow):文档内部的元素的流动方向。分为 display:block、display:inline 和 display:inline-block 三种。目前 HTML5 标准规定元素既可以是内联元素，也可以是块级元素，主要看 display 写了那种。
-   盒模型:有 content-box 和 border-box 两种盒模型，content-box 的宽度 width=内容宽度，border-box 的 width=内容宽度+padding+border 三者总和。

## 布局

1. float 布局
   子元素加上 float:left 或 float:right，父元素 class 属性内加上 clearfix，选择器这样写".clearfix {...}"
2. flex 布局
    - flex container 的样式
        - 使元素变为 flex 容器
          display:flex 或 display:inline-flex
        - 改变主轴流动方向(注：主轴方向不同会影响对齐方式)
          flex-direction:row(从左到右)|row-reverse(从右到左)|column(从上到下)|column-reverse(从下到上)
        - 换行
          flex-wrap:nowrap(不换行)|wrap(换行)|wrap-reverse(从下到上换行)
        - 主轴对齐方式
          justify-content:flex-start|flex-end|center|space-between|space-around|space-evenly
        - 次轴对齐方式
          align-content:flex-start|flex-end|center|stretch
    - flex item 的属性
        - order:0,1,...排序
        - flex-grow 变胖
        - flex-shrink 变瘦
3. grid 布局
   被称为面向未来的布局，尤其擅长不规则布局，据说暂时不推荐使用。

## CSS 定位

1. position:static(默认值，表示呆在文档流里)|relative(相对定位，但未脱离文档流！！！多配合 z-index 使用)|absolute(绝对定位，定位基准是祖先元素中距离最近的第一个 position 不是 static 的元素)|fixed(固定定位，定位基准是视窗，可能有 bug)
2. 层叠上下文：每个层叠上下文都是独立的小世界(世界内 z-index 可以相互比较，外界的 z-index 不行），创建层叠上下文的方式如下:
    - html
    - z-index 值不为 auto 的绝对定位或相对定位元素
    - opacity 属性值小于 1 的元素
    - transform 属性值不为 none 的元素
    - fixed 与 sticky 定位
    - z-index 的值不为 auto 的 flex 子项

## CSS 动画

1. 浏览器渲染过程

    1. 根据 HTML 构建 HTML 树（DOM）
    2. 根据 CSS 构建 CSS 树（CSSOM）
    3. 将两棵树合并成一颗渲染树（render tree）
    4. Layout 布局（文档流、盒模型、计算大小和位置）
    5. Paint 绘制（把边框颜色、文字颜色、阴影等画出来）
    6. Composite 合成（根据层叠关系展示画面）

2. CSS 动画优化

    JS 优化:使用 requestAnimationFrame 代替 setTimeout 或 setInterval。
    CSS 优化:使用 will-change 或 translate。

3. CSS 动画的两种做法(transform 与 animation)

    - transform 属性
        - 位移 translate
        - 缩放 scale
        - 旋转 rotate
        - 倾斜 skew
    - transition 属性
        - 作用：补充中间帧
        - 语法：transition：属性名 时长 过渡方式 延迟
    - [transform 实例](http://js.jirengu.com/mojur/5/edit?html,css,output)

    - animation 属性
        - 语法：animation：时长 过渡方式 延迟 次数 方向 填充方式 是否暂停 动画名
    - [animation 实例](http://js.jirengu.com/dibeg/3/edit?html,css,output)

![end](./end.png)
