---
comments: true
---

## 分析 & 优化

- [Be aware of common issues](https://developer.android.com/topic/performance/vitals/launch-time#common)

### React Native

- 分包(code split)：[react-native-multibundler](https://github.com/smallnew/react-native-multibundler)、[metro-code-split](https://github.com/wuba/metro-code-split)
- 模块懒加载模块require:[react-native-bundle-splitter](https://github.com/kirillzyusko/react-native-bundle-splitter)


### React

- 分包：[代码分离](https://webpack.docschina.org/guides/code-splitting/)


## 监控

React Native启动监控

- 冷启动：SceneTracker
```javascript
//启动时间
import  SceneTracker from 'react-native/Libraries/Utilities/SceneTracker';
SceneTracker.addActiveSceneChangedListener((scene: Scene)=>{
    var startMs = new Date().getTime();
    console.log('runApplication start', scene);
});
```

- 启动时间监控：[react-native-startup-time](https://github.com/doomsower/react-native-startup-time)

- 基于Flipper的性能监控：[shopify/react-native-performance](https://github.com/Shopify/react-native-performance)



### TTI 

- [携程页面性能](https://mp.weixin.qq.com/s?__biz=MjM5MDI3MjA5MQ==&mid=2697269379&idx=1&sn=1227a77caf29ae0e732d976f3f909540&scene=21#wechat_redirect)
- [shopify TTI](https://shopify.engineering/measuring-react-native-rendering-times)

携程的TTI只针对页面，shopify则更广，包括应用启动TTI、页面切换TTI、页面再次刷新TTI。携程页面初始化为开始时间，TTI计算携程认为掐头去尾的页面区域存在大于两组的文字则是截止时间,这个计算方式更像FCP指标而不是TTI指标。

shopify TTI 开始时间

- 应用启动TTI：Application#onCreate为开始时间
- 页面切换TTI：用户点击跳转事件为开始时间
- 页面再次刷新TTI: 刷新时间触发为开始时间，比如用户下拉

shopify认为完全显示出来才是截止时间。

## TTI：案例

- 布局层级过深 、过度绘制等问题

## 参考资料

[Time to interactive](https://developer.mozilla.org/en-US/docs/Glossary/Time_to_interactive)

[前端监控系列3 ｜ 如何衡量一个站点的性能好坏](https://juejin.cn/post/7143201009781702687)