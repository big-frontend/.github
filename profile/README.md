# 大前端 👋

一款跨平台框架必然涉及到两部分，前端与后端，前端为基于js或者dart语言创建的框架，后端为系统平台，提供硬件能力。

占大多数市场的桌面客户端系统有Windows、macOS、Android、iOS，浏览器分为手机浏览器与电脑浏览器，这些客户端统称为大前端，而在这些平台上面又衍生出了微信小程序、Flutter、React Native等跨平台的框架，这些框架主要是通过bright，将前端框架与系统平台连接起来从而实现跨平台。还有一种跨平台，通过编译将一种语言翻译到各个系统平台能识别的机器码或者字节码从而实现跨平台，Kotlin 与 Swift。

所以大前端机会涉及到这么一些关键字: React 全家桶(jsx、React、React Native、Expo)、微信小程序(js)、Flutter(dart)、Jetpack Compose(kotlin)、SwiftUI(swift)、Android、iOS等。

## 混合开发框架
- [dcloudio/uni-app](https://github.com/dcloudio/uni-app)、[taro](https://github.com/NervJS/taro)：uni-app、taro都是为了抹平React Native、各家小程序js框架的差异
- [expo](https://github.com/expo/expo/tree/master) & [facebook/react-native](https://github.com/facebook/react-native) & [react-navigation](https://github.com/react-navigation/react-navigation):Expo是React Native的工程化落地项目，更适合做业务
- [flutter](https://github.com/flutter/flutter):相比较于React Native项目，Flutter整个生态更加完整，工程化做得更好，可以用一个粗糙公式表示Flutter = Expo + React Native+生态贡献的代码。
- 微信小程序的前端框架：[tina](https://github.com/tinajs/tina)

## UI

- MD
  - [mui/material-ui for react](https://github.com/mui/material-ui)
  - [xotahal/react-native-material-ui](https://github.com/xotahal/react-native-material-ui)
  - [material-components](https://github.com/material-components/material-components)：google官方基于android 、iOS 、flutter、Web(HTML5)定制的MD组件

- Ant Design
  - [ant-design](https://github.com/ant-design/ant-design)：蚂蚁官方基于Vue和React两种框架定制的UI组件

- WeChat UI
  - [weui](https://github.com/Tencent/weui/blob/master/README_cn.md)：微信小程序官方UI组件
  - [wux-weapp](https://github.com/wux-weapp/wux-weapp)
  
- 各种自定义Android原生UI
  - [awesome-github-android-ui](https://github.com/opendigg/awesome-github-android-ui)
  - [awesome-android-ui](https://github.com/wasabeef/awesome-android-ui)
  
## 构建
- Android
  - Gradle
- React Native
  - Metro
- React
  - webpack
  
## 动态性

>ps:插件化、分包虽然说法不同但是从使用场景却比较相识，目的都是将apk(jsbundle)安装业务拆分为业务apk(bundle)与基础apk(jsbundle)，所以下面统一叫做分包。

动态性主要从两方面表现：分包与热修复

- Android
  - 插件化：[RePlugin](https://github.com/Qihoo360/RePlugin)
  - 热修复：[tinker](https://github.com/Tencent/tinker)、[Robust](https://github.com/Meituan-Dianping/Robust):前者需要重启应用patch才生效，后者实时生效。

- React Native
  - 分包(code split)：[react-native-multibundler](https://github.com/smallnew/react-native-multibundler)、[metro-code-split](https://github.com/wuba/metro-code-split)

  - 热修复(code push)：[react-native-code-push](https://github.com/microsoft/react-native-code-push)
 
- React
  - 分包：[代码分离](https://webpack.docschina.org/guides/code-splitting/)

## APM
### 稳定性
- Android
  - bugly：公认最好用的第三方平台
  - firebase：google专为大前端打造的产品，网络环境不符合天朝
- React Native
  - Sentry
### 卡顿、启动、内存、包体积
- Android
  - [matrix](https://github.com/Tencent/matrix)：全部包含
- React Native
  - [react-native-bundle-splitter](https://github.com/kirillzyusko/react-native-bundle-splitter)： 启动优化，将不需要的进行懒加载模块require
  - [react-native-bundle-visualizer](https://github.com/IjzerenHein/react-native-bundle-visualizer)：包体积分析
  
  
