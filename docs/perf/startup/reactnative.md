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


## TTI：案例

- 布局层级过深 、过度绘制等问题

## 参考资料

[Time to interactive](https://developer.mozilla.org/en-US/docs/Glossary/Time_to_interactive)

[前端监控系列3 ｜ 如何衡量一个站点的性能好坏](https://juejin.cn/post/7143201009781702687)