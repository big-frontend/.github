
## 1.分析

### 分析思路
- 静息态内存分析(优化app在后台时的内存，防止被llk):做内存分析，统计大图加载；动画播放；内存泄露；数据结构不合理
- 运行时动态内存分析(优化OOM问题)：

### 分析工具
- [memory profile](https://developer.android.com/studio/profile/memory-profiler)
- [内存分析工具 MAT 的使用](http://www.cnblogs.com/tianzhijiexian/p/4268131.html)

mat 的坑

- android hprof 转为mat hprof：hprof-conv android.hprof mat.hprof
- 新版mat必须支持jdk11 ，在ini文件首行配置：
```
window:
-vm
D:/android-studio/jre/bin/javaw.exe

macos:
-vm
/Applications/dev/Android Studio.app/Contents/jre/Contents/Home/bin
```

## 2.内存优化
- 设备分级
    1. 设备分级:对于低端设备可以关闭动画；使用RBG_565
    2. 缓存管理:设计一套统一的缓存管理机制
    3. 进程模型：一个空进程占用10m，减少应用启动的进程数，减少常驻进程
    4. 安装包大小：推出lite版app
- 图片优化
    1. 统一图片库：低端机使用使用RBG_565、更加严格的缩放算法，使用Glide、Fresco
    2. 统一监控：大图监控(图片长度超过View的大小,及时弹出提醒弹窗，超宽率)、重复图片监控(bitmap的像素完全相同，但是有多个对象存在，通过Hprof分析检测)、图片总内存(更加不同系统、屏幕分辨率等不同维度统计图片占用的内存，便于在oom知道图片内存占用量)
    3. 内存泄漏：同一个对象泄漏、新对象泄漏。
            1.java内存泄漏：难做线上监控，因为hprof内存快照文件太大，可以对其进行裁剪压缩。比如一个 100MB 的文件裁剪后一般只剩下 30MB 左右，使用 7zip 压缩最后小于 10MB，增加了文件上传的成功率。
            2.oom监控：美团的Probe，风险较大，可能会造成二次崩溃
            3.native内存监控：malloc debug or malloc hook，不稳定
            4.针对无法重编 so 的情况：针对可重编的 so 情况


## 3.内存监控
- [LeakCanary](https://github.com/square/leakcanary)
- [Matrix ResourceCanary](https://github.com/Tencent/matrix/wiki/Matrix-Android-ResourceCanary)
- [大图监控]()



## 案例
- 静态变量持有短生命的对象
- 单例模式导致
- 无限循环属性动画导致。

## 更多阅读
- [Android 内存暴减的秘密](https://cloud.tencent.com/developer/article/1013705)
- [探索 Android 内存优化方法](https://juejin.cn/post/6844903897958449166#heading-35)
- [图解 Java 垃圾回收算法及详细过程！](https://xie.infoq.cn/article/9d4830f6c0c1e2df0753f9858)
- [JVM 内存分析工具 MAT 的深度讲解与实践——进阶篇](https://juejin.cn/post/6911624328472133646#heading-24)