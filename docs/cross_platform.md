---
comments: true
---

## 跨平台框架对比

跨平台框架\平台 |小程序 |浏览器(browser) |鸿蒙(harmony) | android/ios/window/macos/linux
---|---|---|----|---
KMP(Compose)|  | ✅| |  ✅
[flutter](https://github.com/flutter/flutter) | |✅ | ✅ | ✅
[expo](https://github.com/expo/expo/tree/master) & [facebook/react-native](https://github.com/facebook/react-native)  | |✅ |✅ | ✅
[taro](https://github.com/NervJS/taro) |✅ |✅ |✅ | ✅
[dcloudio/uni-app](https://github.com/dcloudio/uni-app) |✅ |✅ |✅ | ✅

> ps
> - dcloudio/uni-app、taro：uni-app、taro都是为了抹平React Native、各家小程序js框架的差异
> - expo & facebook/react-native & [react-navigation](https://github.com/react-navigation/react-navigation):Expo是React Native的工程化落地项目，更适合做业务
> - flutter:相比较于React Native项目，Flutter整个生态更加完整，工程化做得更好，可以用一个粗糙公式表示Flutter = Expo + React Native+生态贡献的代码。
> - 微信小程序的前端框架：[tina](https://github.com/tinajs/tina)
> flutter support harmony：https://gitee.com/openharmony-sig/flutter_flutter  ， react support harmony： https://gitee.com/openharmony-sig/ohos_react_native  > 

时下最潮、最下饭的技术flutter也有缺点，不支持动态化。不过需要高手改造支持动态化，有较高的技术门槛，但是React Native却恰恰相反。不仅支持就连Facebook造的Hermes都动态支持读取Hermes的字节码，所以React Native天然更适合电商项目。

### kmp、taro 技术探索

[spacecraft-kmp](https://github.com/big-frontend/spacecraft-kmp) 、[spacecraft-taro](https://github.com/big-frontend/spacecraft-taro)

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
