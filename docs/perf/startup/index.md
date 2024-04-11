---
comments: true
---
# 启动(Startup)
对于react native这样通过桥实现的跨平台框架，启动到渲染过程常常出现白屏、文字渲染错位问题，再加上启动与渲染又是紧密相关，所以两者的监控指标都很重要。

## 启动指标

Vitals提供指标(指标存疑，[App startup time](https://developer.android.com/topic/performance/vitals/launch-time))

- 冷启动(cold)：大于5s温启动需优化
- 温启动(warn)：大于2s温启动需优化
- 热启动(hot)：大于1.5s温启动需优化
- 初步显示所用时间(The time to initial display,TTID)：第一帧之前的启动耗时
- 完全显示所用时间 (The Time to full display,TTFD)：全部展示帧之前的启动耗时

Matrix中指标

- 冷启动(applicationCost、firstScreenCost、coldCost)：大于10冷启动需优化
- 温启动(warmCost)：大于4s温启动需优化


### TTI

除了TTI还有分开算有启动之后开始首次渲染FP &&FCP，渲染出主要内容的时间FMP && LCP && SI，可交互的时间TTI && TBT。

先来看看可交互时间(Time to Interactive,TTI)在react native中一些公司对其定义。

shopify's TTI
> At this point, you might start wondering what is considered "rendered"? The thing is, React Native's render doesn't guarantee that the screen is already interactive. Our library injects an invisible marker view with a native counterpart that reports that the view actually did move to the window on the native side. It allows measuring actual end-to-end performance, including React Native to native bridge communication time. Therefore, this is what we consider TTI—the time a screen takes to get rendered on the native side and become interactive to the user.

携程TTI
> 一般在收到统计页面性能需求的时候，开发人员最常规的做法是在页面初始化的时候，设置一个时间点，然后在渲染所需的一个(组)服务发送完，页面渲染之后，设置一个结束点，两者相减，就是页面的可交互时间。







