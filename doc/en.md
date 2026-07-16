> Template version: v0.4.0

<p align="center">
  <h1 align="center"> <code>react-native-status-bar-height</code> </h1>
</p>

This project is based on [react-native-status-bar-height](https://github.com/ovr/react-native-status-bar-height)


 The version correspondence details are as follows:

| Name | Version | Release Information | Supported RN Version | Supported Autolink | Compile API Version | Community Baseline Version | npm Address     |
| --------------| -------------- | ------------------------------ | ------------- | ------------- |------------------------ | ------------- | ------------- |
| @react-native-ohos/react-native-status-bar-height | ~ 2.6.1   | [Github Releases](https://github.com/react-native-oh-library/react-native-status-bar-height/releases) | 0.82.\*/0.77.\*/0.72.* | No | API12+ | 2.6.0| [Npm Address](https://www.npmjs.com/package/@react-native-ohos/react-native-status-bar-height) | 


## 1. Installation and Usage
Go to the project directory and execute the following instruction:

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

The following code shows the basic use scenario of the repository:

> [!WARNING] The name of the imported repository remains unchanged.

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

## 2. Constraints

### 2.1 Compatibility

This document is verified based on the following versions:

1. RNOH: 0.72.20; SDK: HarmonyOS NEXT Developer Beta1; IDE: DevEco Studio 5.0.3.200; ROM: 3.0.0.18;
2. RNOH: 0.77.18; SDK: HarmonyOS 6.0.0 Release SDK; IDE: DevEco Studio 6.0.0.868; ROM: 6.0.0.112;
3. RNOH: 0.82.1; SDK: HarmonyOS 6.0.0 Release SDK; IDE: DevEco Studio 6.0.0.858; ROM: 6.0.0.112;

## 3. Properties

> [!TIP] The **Platform** column indicates the platform where the properties are supported in the original third-party library.

> [!TIP] If the value of **HarmonyOS Support** is **yes**, it means that the HarmonyOS platform supports this property; **no** means the opposite; **partially** means some capabilities of this property are supported. The usage method is the same on different platforms and the effect is the same as that of iOS or Android.

| Name | Description | Type | Required | Platform | HarmonyOS Support |
| --- | --- | --- | --- | --- | --- |
| getStatusBarHeight | Get the status bar height of the current device | `func` | yes | iOS,Android | yes |
| isIPhoneX | Whether it is an iPhoneX. | `function` |  yes | iOS | no |
| isIPhoneXMax | Whether it is an iPhoneX Max. | `function` |  yes | iOS | no |
| isIPhone12 | Whether it is an iPhone12. | `function` |  yes | IOS | no |
| isIPhone12Max | Whether it is an iPhone12 Max. | `function` |  yes | iOS | no |
| isIPhoneWithMonobrow | Whether it is an iPhone with Monobrow. | `function` |  yes | IOS | no |
| isExpo | whether to use Expo. | `function` |  yes | iOS,Android | no |

## 4. Known Issues

## 5. Others
isIPhoneX, isIPhoneXMax, isIPhone12, isIPhone12Max, and isIPhoneWithMonobrow are interfaces used to determine iPhone models, but HarmonyOS does not support them and they are not implemented. 

isExpo is used to determine whether the Expo framework is being used, but HarmonyOS does not support using the Expo framework and it is not implemented.
## 6. License

This project is licensed under [The MIT License (MIT)](https://github.com/ovr/react-native-status-bar-height/blob/master/LICENSE).

