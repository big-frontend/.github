---
comments: true
---

## 分析 & 优化

- [Be aware of common issues](https://developer.android.com/topic/performance/vitals/launch-time#common)

## 监控

Matrix中Android端实现

- 冷启动：启动Application 到 Activity#onWindowFocusChange
- 温启动：应用进程还没有从lruprocess移除时，启动Activity 到 Activity#onWindowFocusChange