---
comments: true
---

# 卡顿(Jank)

每秒帧数(帧率,60fps) 或者每帧耗时(16ms/frame)都可以用来衡量应用的流畅度。

## 指标

Vitals提供指标(指标存疑，[Tracking jank](https://developer.android.com/topic/performance/vitals/tracking_jank))：
```
慢帧(16ms ~ 700ms): 最多掉44帧
冻帧(700ms ~ 5s)：最多掉313帧
ANR(5s，Android平台特有指标)
```

Matrix提供指标：
```java
public static final int DEFAULT_DROPPED_NORMAL = 3;
public static final int DEFAULT_DROPPED_MIDDLE = 9;
public static final int DEFAULT_DROPPED_HIGH = 24;
public static final int DEFAULT_DROPPED_FROZEN = 42;
```


