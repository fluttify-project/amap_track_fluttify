![Logo](https://github.com/fluttify-project/fluttify-core-example/blob/develop/other/Logo-Landscape.png?raw=true)

# 高德地图 猎鹰组件 Flutter插件

[demo apk下载](https://github.com/fluttify-project/fluttify-project/raw/master/resources/amap_track_fluttify/%E7%8C%8E%E9%B9%B0-2020-09-14.apk)

# Fluttify系列插件
|  名称  | 描述 | 仓库 |
|:-----:|:-----:|:-----:|
| [高德地图](https://github.com/fluttify-project/amap_map_fluttify)  |  高德地图地图组件, 提供地图控件 | [![pub package](https://img.shields.io/pub/v/amap_map_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_map_fluttify) |
| [高德定位](https://github.com/fluttify-project/amap_location_fluttify)  |  高德地图定位组件, 提供独立的定位功能 | [![pub package](https://img.shields.io/pub/v/amap_location_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_location_fluttify) |
| [高德搜索](https://github.com/fluttify-project/amap_search_fluttify)  |  高德地图搜索组件, 提供poi搜索等功能 | [![pub package](https://img.shields.io/pub/v/amap_search_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_search_fluttify) |
| [高德猎鹰](https://github.com/fluttify-project/amap_track_fluttify)  |  高德地图猎鹰组件, 提供实时定位采集功能 | [![pub package](https://img.shields.io/pub/v/amap_track_fluttify.svg)](https://pub.Flutter-io.cn/packages/amap_track_fluttify) |
| [百度地图](https://github.com/fluttify-project/bmap_map_fluttify)  |  百度地图, 包含了地图控件, 定位以及搜索poi等功能 | [![pub package](https://img.shields.io/pub/v/bmap_map_fluttify.svg)](https://pub.Flutter-io.cn/packages/bmap_map_fluttify) |
| [百度人脸识别](https://github.com/fluttify-project/baidu_face_flutter)  |  百度人脸识别, 提供活体检测等功能 | [![pub package](https://img.shields.io/pub/v/baidu_face_flutter.svg)](https://pub.Flutter-io.cn/packages/baidu_face_flutter) |
| [网易直播](https://github.com/fluttify-project/netease_live_fluttify)  |  网易直播推流组件 | [![pub package](https://img.shields.io/pub/v/netease_live_fluttify.svg)](https://pub.Flutter-io.cn/packages/netease_live_fluttify) |
| [网易云信](https://github.com/fluttify-project/nim_fluttify)  |  网易云信 IM组件 | [![pub package](https://img.shields.io/pub/v/nim_fluttify.svg)](https://pub.Flutter-io.cn/packages/nim_fluttify) |
| [腾讯直播](https://github.com/fluttify-project/tencent_live_fluttify)  |  腾讯直播, 包含推流组件和播放组件 | [![pub package](https://img.shields.io/pub/v/tencent_live_fluttify.svg)](https://pub.Flutter-io.cn/packages/tencent_live_fluttify) |
| [腾讯IM](https://github.com/fluttify-project/tim_fluttify)  |  腾讯IM组件 | [![pub package](https://img.shields.io/pub/v/tim_fluttify.svg)](https://pub.Flutter-io.cn/packages/tim_fluttify) |
| [腾讯地图](https://github.com/fluttify-project/tmap_map_fluttify)  |  腾讯地图组件 | [![pub package](https://img.shields.io/pub/v/tmap_map_fluttify.svg)](https://pub.Flutter-io.cn/packages/tmap_map_fluttify) |
| [讯飞语音合成](https://github.com/fluttify-project/xftts_fluttify)  |  腾讯语言合成组件, 提供文字转语言功能 | [![pub package](https://img.shields.io/pub/v/xftts_fluttify.svg)](https://pub.flutter-io.cn/packages/xftts_fluttify) |
| [极光统计](https://github.com/fluttify-project/janalytics_fluttify)  |  极光统计组件, 提供异常上报等功能 | [![pub package](https://img.shields.io/pub/v/janalytics_fluttify.svg)](https://pub.flutter-io.cn/packages/janalytics_fluttify) |
| [阿里云RTC](https://github.com/fluttify-project/ali_rtc_fluttify)  |  阿里云实时音视频 | [![pub package](https://img.shields.io/pub/v/ali_rtc_fluttify.svg)](https://pub.flutter-io.cn/packages/ali_rtc_fluttify) |
| [环信](https://github.com/fluttify-project/easemob_im_fluttify)  |  环信IM | [![pub package](https://img.shields.io/pub/v/easemob_im_fluttify.svg)](https://pub.flutter-io.cn/packages/easemob_im_fluttify) |
| [未完待续...](https://github.com/fluttify-project)  |  如有其它需求, 请联系qq 382146139 | ![fluttify](https://img.shields.io/badge/fluttify-welcom-green) |

## 依赖
```yaml
dependencies:
  flutter:
    sdk: flutter
  amap_track_fluttify: ^x.x.x
```

## 配置
### Android
1. 在`AndroidManifest.xml`的`<application>`标签下配置从高德开发者后台申请的key.
```xml
<application
    android:name="io.flutter.app.FlutterApplication"
    android:label="amap_track_fluttify_example"
    android:icon="@mipmap/ic_launcher">
    <meta-data
            android:name="com.amap.api.v2.apikey"
            android:value="你的key"/>
    <!--... 其他内容-->
</application>
```
2. 注意在app/build.gradle的android块中配置签名信息, 并在buildTypes块中指定签名信息, 否则将无法匹配到你在高德后台配置的key, 例如:
```groovy
android {
    signingConfigs {
        release {
            keyAlias 'amap_track_demo'
            keyPassword 'amap_track_demo'
            storeFile file('../amap_track_demo.jks')
            storePassword 'amap_track_demo'
        }
    }

    buildTypes {
        debug {
            signingConfig signingConfigs.release
        }
        profile {
            signingConfig signingConfigs.release
        }
        release {
            signingConfig signingConfigs.release
        }
    }
}
```
3. 由于猎鹰SDK直接包含了定位SDK的代码, 导致不能与定位SDK共存, 解决方案为:
    1. 使用Android Studio打开android工程;
    2. 找到amap_location_fluttify模块的`build.gradle`文件;
    3. 74行, 修改`api 'com.amap.api:location:5.1.0'` 为 `compileOnly 'com.amap.api:location:5.1.0'`; 此处修改意为"只在编译期间可见定位SDK, 不包含在最终的apk中", 所以能解决猎鹰SDK和定位SDK的冲突.
    4. **此处修改为临时改动, 当定位插件版本升级时, 会覆盖掉此处的修改, 所以当定位插件升级时, 要留意这里, 需要重新改动回`compileOnly`**;
4. 权限无需另外申明, 定位服务组件无需另外声明, 已在插件中引入;
5. 无需再处理混淆, 已在插件中配置混淆规则;

### iOS
1. 与Android端不同, iOS端的初始化需要在`AmapTrack.instance.init`方法中传入, 具体参考wiki;
2. 定位需要声明权限, 在Info.plist中添加:
```xml
<key>NSLocationWhenInUseUsageDescription</key>
<string>需要定位权限</string>
<key>NSLocationAlwaysUsageDescription</key>
<string>需要定位权限</string>
<key>NSLocationAlwaysAndWhenInUseUsageDescription</key>
<string>需要定位权限</string>
```

## 导入
```dart
import 'package:amap_track_fluttify/amap_track_fluttify.dart';
```

## 使用
参考[wiki](https://github.com/fluttify-project/amap_track_fluttify/wiki).

## 社区
| QQ群 |
| :----------: |
| <img src="https://github.com/fluttify-project/fluttify-project/blob/master/resources/1593774713224_temp_qrcode_share_9993.png?raw=true" height="300"> | 

## LICENSE
> Copyright (C) 2020 yohom
> 
> This program is free software: you can redistribute it and/or modify
> it under the terms of the GNU General Public License as published by
> the Free Software Foundation, either version 3 of the License, or
> (at your option) any later version.
> 
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.
> 
> You should have received a copy of the GNU General Public License
> along with this program.  If not, see <https://www.gnu.org/licenses/>.
 
