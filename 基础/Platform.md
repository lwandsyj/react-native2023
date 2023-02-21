1. OS: 平台android 和 ios

        static OS: 'android' | 'ios';

2. Version: 系统版本

3. select 函数，根据系统选择配置的内容

    方法声明：

        static select(config: Record<string, T>): T;

    config 参数是一个对象，拥有以下几种值：

    + android：

    + ios

    + native

    + default


+ 值为字面量

        const fontReference = Platform.select({
            windows: `/Assets/${fontFile}#${fontFamily}`,
            android: fontBasename,
            web: fontBasename,
            default: fontFamily,
        });

+ 值为对象

        import {Platform, StyleSheet} from 'react-native';

        const styles = StyleSheet.create({
          container: {
            flex: 1,
            ...Platform.select({
              android: {
                backgroundColor: 'green',
              },
              ios: {
                backgroundColor: 'red',
              },
              default: {
                // other platforms, web for example
                backgroundColor: 'blue',
              },
            }),
          },
        });

        android 背景颜色为绿色，ios 背景颜色为红色，web 背景颜色为蓝色

+ 值为函数

        const Component = Platform.select({
            ios: () => require('ComponentIOS'),
            android: () => require('ComponentAndroid'),
        })();

        <Component />;