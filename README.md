# 大前端 👋

一款跨平台框架必然涉及到两部分，前端与后端，前端为基于js或者dart语言创建的框架，后端为系统平台，提供硬件能力。

占大多数市场的桌面客户端系统有Windows、macOS、Android、iOS，浏览器分为手机浏览器与电脑浏览器，这些客户端统称为大前端，而在这些平台上面又衍生出了微信小程序、Flutter、React Native等跨平台的框架，这些框架主要是通过bright，将前端框架与系统平台连接起来从而实现跨平台。还有一种跨平台，通过编译将一种语言翻译到各个系统平台能识别的机器码或者字节码从而实现跨平台，Kotlin 与 Swift。

所以大前端基本涉及到这么一些关键字: React 全家桶(jsx、React、React Native、Expo)、微信小程序(js)、Flutter(dart)、Jetpack Compose(kotlin)、SwiftUI(swift)、Android、iOS等。

## 混合开发框架

- [dcloudio/uni-app](https://github.com/dcloudio/uni-app)、[taro](https://github.com/NervJS/taro)：uni-app、taro都是为了抹平React Native、各家小程序js框架的差异
- [expo](https://github.com/expo/expo/tree/master) & [facebook/react-native](https://github.com/facebook/react-native) & [react-navigation](https://github.com/react-navigation/react-navigation):Expo是React Native的工程化落地项目，更适合做业务
- [flutter](https://github.com/flutter/flutter):相比较于React Native项目，Flutter整个生态更加完整，工程化做得更好，可以用一个粗糙公式表示Flutter = Expo + React Native+生态贡献的代码。
- 微信小程序的前端框架：[tina](https://github.com/tinajs/tina)

时下最潮、最下饭的技术flutter也有缺点，不支持动态化。不过需要高手改造支持动态化，有较高的技术门槛，但是React Native却恰恰相反。不仅支持就连Facebook造的Hermes都动态支持读取Hermes的字节码，所以React Native天然更适合电商项目。

## 技术分享主题

Android技术已经走过了十多年了，从技术的增长期到技术的爆炸期，以及现在的稳定期，大量的技术变化带来了效率与性能的提高。在这个项目中，我们会讨论如今Android、跨平台(React Native 、Flutter、微信小程序)项目的工程化，拆分为三个主题：Architecture、DevOps、Performance

- [Architecture](https://big-frontend.github.io/pisces/arch/design_patterns/): 模块化、插件化、组件化、热修复、动态化
- [DevOps](https://big-frontend.github.io/pisces/devops/)：编码、测试、发布、运营
- [Performance](https://big-frontend.github.io/pisces/perf/)：Application Performance Monitoring 、Profiling 、 Optimization
- [bundles-assembler 项目wiki](https://github.com/electrolyteJ/bundles-assembler/wiki)

更多大前端的技术探索 👉🏻 [🔥pisces](https://big-frontend.github.io/pisces/)
