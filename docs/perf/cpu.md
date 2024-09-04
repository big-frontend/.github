---
comments: true
---

# CPU

Tracer是trace cpu工具的统称，可用来分析卡顿、启动、渲染问题，帮忙我们快速找出慢函数。

## 术语

- wall duration:函数执行时间(包含等待时间)，函数wall时间 = 运行时间+其他时间(阻塞(io、加锁)、就绪等情况)
- wall self time:函数执行时间(不包含等待时间)
- cpu duration:cpu执行时间 = cpu在用户态运行时间+cpu在内核态运行时间
- cpu self time

[墙上时钟时间 ，用户cpu时间 ，系统cpu时间](https://www.cnblogs.com/vinozly/p/5078755.html)

## Tracer

### 各家公司的Android trace分析工具

| tracer  |类型|图表类型|性能损耗
| --- | --- |--- | ---|

|  微信的[TraceCanary](https://github.com/Tencent/matrix/wiki/Matrix-Android-TraceCanary) | ... |...|...|
| facebook的[profilo](https://github.com/facebookincubator/profilo) |  sample和instrument|...|sample和instrument性能损耗小，但是instrument存在兼容性问题
|uber的[Nanoscope](https://github.com/uber/nanoscope)|instrument|Call Chart|在ArtMethod执行入口和执行结束位置增加埋点代码，性能损耗小
| android的traceview | instrument 和 sample|Call Chart|instrument traceview基于android runtime函数调用的event，性能损耗大;sample  traceview提供的sample类型采集trace，性能损耗比instrument小
|  字节[btrace](https://github.com/bytedance/btrace/blob/master/README.zh-CN.md) | sample|Call Chart|...
| android的systrace |sample|Call Chart|systrace 封装linux的ftrace，性能损耗小
| android的[simpleperf](https://android.googlesource.com/platform/system/extras/+/master/simpleperf/doc/README.md)|sample|Frame Chart|部分功能封装systrace ,利用 CPU 的性能监控单元（PMU）提供的硬件 perf 事件，性能损耗小

> ps:instrument类型的trace工具，既可以通过命令行脚本start/stop录制下trace文件，也可以通过代码中的Debug#startMethodTracing/stopMethodTracing录制下两函数范围内的trace文件。sample类型的trace工具，仅通过命令行脚本start/stop录制下埋了Trace#beginSection/endSection的trace文件。

> systrace:java代码使用Trace#beginSection/endSection, cpp代码使用ATrace_beginSection/ATrace_endSection 

> sample traceview: java代码调用Debug#startMethodTracingSampling/stopMethodTracing

> instrument traceview: java代码使用Debug#startMethodTracing/stopMethodTracing

android团队提供的trace ui

- Android Studio CPU Profiler:整合了 systrace(命令行：`py -2 systrace.py --help`) 、traceview、simpleperf
- [Perfetto](https://perfetto.dev/docs/) 命令行工具（Android 10 及更高版本）
- System tracing utility:android手机设置中开发者模式提供的“系统跟踪”功能


### React Native框架提供的trace

| lang  |trace类  |
| --- | --- |
|  javascript | Systrace.js(systrace工具埋入trace数据)
| cpp | ... 
|java|SystraceMessage.java/Systrace.java
|OC|...

## 参考资料
[Profiling](https://reactnative.dev/docs/profiling)

[Understanding Systrace](https://source.android.com/docs/core/tests/debug/systrace)

[Overview of system tracing](https://developer.android.com/topic/performance/tracing/)

[Catapult](https://chromium.googlesource.com/catapult/+/HEAD/README.md)

