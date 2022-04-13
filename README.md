# css-route
css路线

## 学习路线
+ [CSS基础及入门](https://coding.imooc.com/class/164.html)[11小时]
+ [前端主流布局进阶与实战](https://coding.imooc.com/class/chapter/527.html#Anchor)[16小时]

## 笔记
+ CSS (Cascading Style Sheet 层叠样式表)梳理
    + CSS 基础
        + 选择器（ 属性:值 ）
            + 作用
                + 用于匹配HTML元素
                + 有不同的匹配规则
                + 多个选择器可叠加
            + 解析与性能：从右到左，及从小到大进行更快速的解析
            + 分类
                + 元素选择器 a{} 权重 +1 
                + 伪元素选择器 ::before{} 表示一个真实存在的元素的样式 权重 +0
                + 类选择器：.link{}  权重 +10 
                + 属性选择器：[type =radio]{} 权重 +10 
                + 伪类选择器  :hover{} 表示一个元素某种状态的样式 权重 +10
                + ID选择器： #id{}  权重 +100 
                + 组合选择器： [type=checkbox]+label{} 权重 +0
                + 否定选择器   :not(.link){} 权重 +0
                + 通用选择器 *{} 权重 +0
            + 选择器权重
                + !important优先级最高
                + 元素属性 优先级高
                + 相同权重 后写的生效
        + 非布局样式
            + 行高
                + 行高的构成。由一行的linebox决定的，linebox是由inlinebox组成的，inlinebox的高度决定行高的高度
            + 背景
            + 边框
                + 线型，大小，颜色
                + 边框背景图
                + 边框衔接（三角形）
            + 滚动
                + 滚动行为和滚动条
            + 文字折行
                + overflow-wrap 通用换行控制
                    + 是否保留单词 
                + word-break 针对多字节文字
                    + 中文句子也是单词
                + white-space 空白处是否断行
            + 装饰属性：
                + 字重：font-weight
                + 斜体：font-style:itatic
                + 下划线：text-decoration
                + 指针： cursor
        + CSS 布局
            + 布局基础属性：
                + diplay。确定元素的显示类型。
                    + block/ 独立宽高，默认占据一行
                    + inline/默认不占据一行
                    + inline-block/ 对内有自己的宽高，对外不占据一行
                + 确定元素的位置。
                    + static/ 按照文档流
                    + relative/ 偏移大小是相对于元素本身的
                    + absolute/ 脱离文档流，偏移大小是相对于最近的父元素
                    + fixed/ 脱离文档流，相对于可视区域或者屏幕（viewport）
                    + z-index/ 相对于人眼，哪个标签在前
                + flexbox 弹性盒子，盒子本来就是并列的，指定宽度即可。低版本IE不支持
                + float布局。
                    + 脱离文档流，但不脱离文本流
                    + 对自身的影响：形成“块"（BFC）
                    + 位置尽量靠上
                    + 对兄弟元素的影响：上面贴非float元素，旁边贴float元素，不影响其他块级元素位置，影响其他块级元素的文本
                    + 对父级元素的影响：从布局上""消失"
                    + 清除浮动
                + inline-block
                    + 像文本一样排block元素
                    + 没有清除浮动等问题
                    + 需要处理间隙
        + 效果属性
            + box-shadow: 盒子阴影
            + text-shadow: 文本阴影
            + border-radius: 圆角矩形
            + background: 背景
            + clip-path:  
        + CSS 动画
            + 动画的原理：视觉暂留作用。画面的渐变
            + 动画类型
                + transition 补间动画
                + ketframe 关键帧动画。相当于多个补间动画
                + 逐帧动画。适用于无法补间计算的动画 
    + CSS 进阶
        +  CSS盒模型的组成
            + 在CSS中，所有的元素都被一个个盒子包围着。盒子的组成：content内容、padding内填充，border边框，margin外边距
                + padding 不能为负值，而margin可以为负值
                + 背景色会平铺到非margin的区域
                + margin-top传递的现象及解决方案
                + margin上下的叠加现象及解决方案
            + 块级盒子和内联盒子
                + 块级盒子：div、p、h1 (display:block)
                    + 独占一行
                    + 支持所有样式
                    + 不写宽度的时候，与父容器宽度相同
                    + 所占区域是一个矩形
                + 内联盒子：span、a、strong (display:inline)
                    + 不会产生换行
                    + 有些样式不支持，例如：width、height
                    + 不写宽度的时候，宽度由内容决定
                    + 所占区域不一定是矩形
            + 自适应盒模型的特性
                + 当盒子不设置宽度时，再添加内部的css属性时，会进行重新计算，往内收缩
            + 标准盒模型与怪异盒模型（IE盒模型）
                + 在标准模型中，如果你给盒设置width和height，实际设置的是content box。padding和 border再加上设置的宽高一起决定整个合盒子的大小
                + 在怪异盒模型中，所有宽度都是可见宽度，所以内容宽度是该宽度减去边框和填充部分。box-sizing:border-box
                + box-sizing : 
                    + content-box:width、height -> content
                    + border-box：width、height ->content + padding + border 
                + 作用：
                    + 量取尺寸时不用再去计算一些值
                    + 解决一些需要设置百分比和盒模型值
            + 浮动
                + 当元素被浮动时，会脱离文档流，根据float的值向左或向右移动，直到它的外边界碰到父元素的内边界或另一个浮动元素的外边界为止,是CSS布局中实现左右布局的一种方式
                + 文档流：文档流是元素在web页面上的一种呈现方式，按照出现的先后顺序进行排列。
                + 清除浮动
                    + clear: clear:both;
                    + BFC: 
                    + 空标签 ： <div style="clear:both;"></div>
                    + .clearfix::after{}
                + 特性
                    + 只会影响后面的元素
                    + 文本不会被浮动的元素覆盖
                    + 具备内联盒子的特性，宽度由内容决定
                    + 具备块级元素的特性，支持所有样式
                    + 浮动放不下，自动换行
            + 定位
                + position属性用于指定一个元素在文档中的定位方式，其中top,right,bottom和left属性则决定了该元素的最终位置
                + 相对定位
                    + 元素是在文档中的正常位置偏移给定的值
                    + 不影响其他元素布局
                    + 相对于自身进行偏移
                + 绝对定位
                    + 绝对定位的元素脱离文档流，绝对定位元素不占据空间
                    + 具备内联盒子特性：宽度由内容决定
                    + 具备块级盒子特性：支持所有样式
                    + 绝对定位元素相对于最近的非static祖先元素定位。当这样的祖先元素不存在时，则相对于可视区定位
                + 固定定位及特性
                    + 固定定位与绝对定位相似，但是会固定在可视区中。
                    + 具备内联盒子特性：宽度由内容决定
                    + 具备块级盒子特性：支持所有样式
                    + 固定定位元素不受祖先元素影响 
                + 粘性定位
                    + 粘性定位可以被认为是相对定位和固定定位的混合。元素在跨特定阈值前卫相对定位，之后为固定定位。