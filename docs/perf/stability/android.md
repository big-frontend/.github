
## Crash 分析 & 优化

## ANR 分析 & 优化
- MessageQueue.nativePollOnce: 
    - 应用超过 100% 导致系统 60% 忙，webview初始化io 占用高，让其空闲在初始化
    - 其他应用超过 100% 导致系统 60% 忙

- Binder.transcat : 
    - 下载时频繁调用 ContentProvider 查询数据导致binder线程池满 
    -  binder 调用耗时
    - wps binder调用耗时

- application no focus windows : 启动 application 超时
- sp waitall
- 线程锁
- HardwareRenderer.nSyncAndDrawFrame阻塞：webview绘制时阻塞，浏览器存在大量过度绘制，优化浏览器 view 数
- 一帧绘制太久导致ANR，打印慢函数可定位
- 内存不足，多次出发gc

## 监控
| java/kotlin crasher| desc
|---|---|
bugly |业界标杆
[xCrash](https://github.com/iqiyi/xCrash)| 
[acra](https://github.com/ACRA/acra)| 捕获前端与收集后端功能完整
Dropbox|Android系统
[Sentry](https://develop.sentry.dev/)| java sentry,sentry提供server+client采集方案

| c/cc crasher| desc
|---|---|
[breakpad](https://github.com/google/breakpad)|权威，跨平台，代码量大
[coffeecatch](https://github.com/xroche/coffeecatch)|实现简介，兼容性问题
[xCrash](https://github.com/iqiyi/xCrash)| 
Dropbox|Android系统
[Sentry](https://develop.sentry.dev/)| cpp sentry,sentry提供server+client采集方案



## 参考资料

- [字节ANR剖析](https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzI1MzYzMjE0MQ==&action=getalbum&album_id=1780091311874686979&scene=173&from_msgid=2247488243&from_itemidx=1&count=3&nolastread=1#wechat_redirect)

- [Fix the problems](https://developer.android.com/topic/performance/vitals/anr#fix)

- [得物App Android Crash治理演进](https://juejin.cn/post/7001060315056046117)

- [得物App ANR监控平台设计](https://juejin.cn/post/7009297034440081422)
