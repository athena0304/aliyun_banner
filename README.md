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

| Tables        | Are           |
| ------------- |-------------  |
| linear      | 动画从头到尾的速度是相同的。 |
| ease      | 默认。动画以低速开始，然后加快，在结束前变慢。 |


#### animation-duration
规定完成动画所花费的时间，以秒或毫秒计。

### animation-timing-function
规定动画的速度曲线。

### animation-delay
规定在动画开始之前的延迟。

### animation-iteration-count
规定动画应该播放的次数。

### animation-direction
规定是否应该轮流反向播放动画。

参数：normal（默认） alternate(动画应该轮流反向播放。)
