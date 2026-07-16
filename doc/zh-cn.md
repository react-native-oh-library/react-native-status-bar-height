> 模板版本：v0.4.0

<p align="center">
  <h1 align="center"> <code>react-native-status-bar-height</code> </h1>
</p>

本项目基于 [react-native-status-bar-height](https://github.com/ovr/react-native-status-bar-height) 开发。

版本所属关系如下：
| 三方库名称    | 三方库版本    | 发布信息     | 支持RN版本    | Autolink     | 编译API版本     | 社区基线版本    | npm地址                |
| ------------ | ------------ | ------------------------------ | ------------- | ------------- |------------------------ | ------------- | ------------- |
| @react-native-ohos/react-native-status-bar-height | ~ 2.6.1   | [Github Releases](https://github.com/react-native-oh-library/react-native-status-bar-height/releases) | 0.82.\*/0.77.\*/0.72.* | 否 | API12+ | 2.6.0| [Npm Address](https://www.npmjs.com/package/@react-native-ohos/react-native-status-bar-height) | 

## 1. 安装与使用

进入到工程目录并输入以下命令：

<!-- tabs:start -->

#### **npm**

```bash
# V2.6.1
npm install @react-native-ohos/react-native-status-bar-height
```

#### **yarn**

```bash
# V2.6.1
yarn add @react-native-ohos/react-native-status-bar-height
```

<!-- tabs:end -->

下面的代码展示了这个库的基本使用场景：

> [!WARNING] 使用时 import 的库名不变。

```ts

import React, { useState } from "react";
import { View, Text, Button, PixelRatio } from "react-native";
import {TestCase, Tester} from "@rnoh/testerino"
import { getStatusBarHeight } from 'react-native-status-bar-height';

const App = (props) => {
    let [statusBarHeight,setData] = useState<number>(0);
    const getstatusbarHeight = () => {
    statusBarHeight = getStatusBarHeight(false);
    setData(statusBarHeight) 
    console.debug(statusBarHeight);
  };
  
  return (
    <Tester style={{flex: 1 , marginTop: 30}}>
      <TestCase itShould={"getstatusbarHeight"}>
        <View style={{ margin: 50, flexDirection: "column", justifyContent: "center" }}>
          <View>
            <Button
              title="getStatusBarHeight"
              onPress={() => getstatusbarHeight()}
            />
            <Text>{"statusBarHeight: "+JSON.stringify(statusBarHeight)+" dp"}</Text>
            <Text>{"statusBarHeight: "+JSON.stringify(PixelRatio.getPixelSizeForLayoutSize(statusBarHeight))+" px"}</Text>
          </View>
        </View>
      </TestCase>
    </Tester>
  );
};

export default App
```

## 2. 约束与限制

### 2.1. 兼容性

本文档内容基于以下版本验证通过：

1. RNOH: 0.72.20; SDK: HarmonyOS NEXT Developer Beta1; IDE: DevEco Studio 5.0.3.200; ROM: 3.0.0.18;
2. RNOH: 0.77.18; SDK: HarmonyOS 6.0.0 Release SDK; IDE: DevEco Studio 6.0.0.868; ROM: 6.0.0.112;
3. RNOH: 0.82.1; SDK: HarmonyOS 6.0.0 Release SDK; IDE: DevEco Studio 6.0.0.858; ROM: 6.0.0.112;


## 3. 属性

> [!TIP] "Platform"列表示该属性在原三方库上支持的平台。

> [!TIP] "HarmonyOS Support"列为 yes 表示 HarmonyOS 平台支持该属性；no 则表示不支持；partially 表示部分支持。使用方法跨平台一致，效果对标 iOS 或 Android 的效果。

| Name | Description | Type | Required | Platform | HarmonyOS Support |
| --- | --- | --- | --- | --- | --- |
| getStatusBarHeight | 获取当前设备状态栏高度 | `function` | yes | iOS,Android | yes |
| isIPhoneX | 是否为 iPhone X | `function` | yes | iOS | no |
| isIPhoneXMax | 是否为 iPhone X Max | `function` | yes | iOS | no |
| isIPhone12 | 是否为 iPhone 12 | `function` | yes | iOS | no |
| isIPhone12Max | 是否为 iPhone 12 Max | `function` | yes | iOS | no |
| isIPhoneWithMonobrow | 是否为带刘海的 iPhone | `function` | yes | iOS | no |
| isExpo | 是否使用 Expo | `function` | yes | iOS,Android | no |


## 4. 遗留问题

## 5. 其他
isIPhoneX，isIPhoneXMax，isIPhone12，isIPhone12Max，isIPhoneWithMonobrow这些接口用于判断IPhone机型，Harmony不支持，未实现。

isExpo是判断是否使用Expo框架，Harmony不支持使用Expo框架，未实现。

## 6. 开源协议

本项目基于 [The MIT License (MIT)](https://github.com/ovr/react-native-status-bar-height/blob/master/LICENSE) ，请自由地享受和参与开源。

