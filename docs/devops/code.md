# 1.代码设计(code design)


# 2.开发(coding)


## 构建

- Android
    - Gradle
- React Native
    - Metro
- React
    - Webpack/Vite/Rollup
 
## 效率工具

- intellij插件开发：[intellij-sdk-code-samples
](https://github.com/JetBrains/intellij-sdk-code-samples)、[IntelliJ Platform Plugin SDK](https://plugins.jetbrains.com/docs/intellij/kotlin-ui-dsl.html#layout-structure)、[IntelliJ Platform UI Guidelines](https://jetbrains.design/intellij/)
- chrome插件开发：[chrome-extensions-samples](https://github.com/GoogleChrome/chrome-extensions-samples)、[extensions](https://developer.chrome.com/docs/extensions/mv3/)


# 3.代码评审(code review)

## 扫描
- 质量扫描：Sonar、Qodana、Infer、Android Linter
- 源代码安全扫描
- 第三方组件安全扫描(sca)
- 开源合规扫描

## 测试

- 覆盖率：[Android增量代码测试覆盖率工具](https://tech.meituan.com/2017/06/16/android-jacoco-practace.html)、JaCoCo
- 自动化测试：单元测试、集成测试等，[自动化测试在美团外卖的实践与落地](https://tech.meituan.com/2022/09/15/automated-testing-in-meituan.html)

# 4. 发布
- sdk发布到maven仓库
- apk/js bundle/插件/补丁发布到蒲公英或者自建发布平台

# 5.性能与稳定性监控
