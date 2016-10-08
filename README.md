# aliyun_banner
阿里云banner模仿

## 一 概述
这次要好好梳理一下css3的这些特性，什么transition啊，animation啊啥的，把每个属性里的每个参数都搞清楚，下次用的时候直接参考这篇文档就好。

## 二 css基础知识

### 2.1 animation

语法：`animation: name duration timing-function delay iteration-count direction;`
举例：`animation: re-banner-slide-40 0.8s cubic-bezier(0.4, 0, 0.2, 1) 0s 1;`

#### animation-name
规定需要绑定到选择器的 keyframe 名称。

例如本文中用到的：
```
@keyframes re-banner-slide-40{
    0%{
        opacity:0;
        -webkit-transform: translate3d(0, 40px, 0);
        -moz-transform: translate3d(0, 40px, 0);
        -ms-transform: translate3d(0, 40px, 0);
        transform: translate3d(0, 40px, 0);
    }
    100%{
        opacity:1;
        -webkit-transform: translate3d(0, 0, 0);
        -moz-transform: translate3d(0, 0, 0);
        -ms-transform: translate3d(0, 0, 0);
        transform: translate3d(0, 0, 0);
    }
}
```

#### animation-duration
规定完成动画所花费的时间，以秒或毫秒计。

#### animation-timing-function
规定动画的速度曲线。使用名为三次贝塞尔（Cubic Bezier）函数的数学函数，来生成速度曲线。您能够在该函数中使用自己的值，也可以预定义的值：

| 值             | 描述           |
| -------------  |-------------  |
| linear         | 动画从头到尾的速度是相同的。 |
| ease           | 默认。动画以低速开始，然后加快，在结束前变慢。 |
| ease-in        | 动画以低速开始。 |
| ease-out       |动画以低速结束。 |
| ease-in-out    | 动画以低速开始和结束。 |
| cubic-bezier(n,n,n,n)  |在 cubic-bezier 函数中自己的值。可能的值是从 0 到 1 的数值。 |

详细讲解和例子点[这里](http://www.jianshu.com/p/d999f090d333#)
#### animation-delay
规定在动画开始之前的延迟。

#### animation-iteration-count
规定动画应该播放的次数。

#### animation-direction
规定是否应该轮流反向播放动画。

参数：normal（默认） alternate(动画应该轮流反向播放。)



### 2.2 transition

语法：`transition: property duration timing-function delay;`
举例：`transition: all 0.5s ease-out;`

看到`duration timing-function delay`这三个参数，在animation和transition里都是一样的。属性可以设置多个，也可以设置多套。

animation与transition最大的区别就是animation可以定义关键帧，而transition不可以。还有就是transition是需要事件或者状态的改变来出发的，而animation是可以一开始就触发，也可以通过状态改变来触发。两者的timing-function都是用的贝赛尔曲线。

> 补充一点：对于transition而言，不管是动态设置的还是非动态设置的过渡效果，只要过渡效果指定的属性值发生了变化就会触发过渡效果。
对于animation而言，如果是非动态设置的，那么页面加载完后（具体是页面加载完还是元素渲染完后触发，没研究）就会触发动画效果；如果是动态设置的，那么设置完后（假设没有设置 delay）就会触发动画效果。后面再改变属性值也不会触发动画效果了，除了一种情况（这种情况不会触发transition定义的过渡效果），就是元素从 display:none 状态变成非 display:none 状态时，也会触发动画效果。[柴肖钧](https://www.zhihu.com/question/19749045/answer/113250349)


一个非常好的教程[点这里](http://learn.shayhowe.com/advanced-html-css/transitions-animations/)
