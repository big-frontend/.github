---
comments: true
---
## 分析 & 优化


卡顿的场景比较多启动卡顿、页面切换卡顿、列表卡顿、执行动画卡顿等，而造成卡顿的原因有很多，比如内存不足触发频繁gc导致主线程阻塞(内存问题)；启动过程中存在慢函数或者锁等待(启动问题)；ui布局层级深或者过度重绘(渲染问题)。内存问题就是用mat等工具分析内存情况，启动问题就用trace工具分析函数耗时，渲染问题可以用Android提供的过度渲染工具与opengl trace工具。


## 监控

- 监控Looper#loop前后的Printer#println方法:开源项目matrix
- 计算ChoreographerCompat.FrameCallback两次时间差：react natvie平台提供的FpsView