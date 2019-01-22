cordova-plugin-x5-webview2
====

本项目fork自[cordova-plugin-x5-webview](https://github.com/jeremyup/cordova-plugin-x5-webview)  
更新到最新的X5 SDK，并适配cordova-android 7.x  

## 使用方法  
在项目的MainActivity中添加
```
import com.tencent.smtt.sdk.QbSdk;

QbSdk.PreInitCallback cb = new QbSdk.PreInitCallback() {

      @Override
      public void onViewInitFinished(boolean arg0) {
        // TODO Auto-generated method stub
        //x5內核初始化完成的回调，为true表示x5内核加载成功，否则表示x5内核加载失败，会自动切换到系统内核。
        Log.d("app", " onViewInitFinished is " + arg0);
        // Set by <content src="index.html" /> in config.xml
      }

      @Override
      public void onCoreInitFinished() {
        // TODO Auto-generated method stub
      }
    };
QbSdk.initX5Environment(this, cb);
```

## 检测是否切换到X5  
```
console.log(navigator.userAgent);
```

## 其他参考  
https://x5.tencent.com/tbs/technical.html#/detail/sdk/1/34cf1488-7dc2-41ca-a77f-0014112bcab7  


Benefits
----

WebView doesn't change depending on Android version
Capabilities: such as WebRTC, WebAudio, Web Components
Performance improvements (compared to older system webviews)

Drawbacks
----

Increased APK size (about 300KB)

Install
----
The following directions are for cordova-cli (most people). Alternatively you can use the Android platform scripts workflow.

Open an existing cordova project, with cordova-android 4.0.0+, and using the latest CLI. X5 variables can be configured as an option when installing the plugin
<br/>Add this plugin   
``$ cordova plugin add cordova-plugin-x5-webview``<br/>  
Build    
``$ cordova build android``

The build script will automatically fetch the X5 WebView libraries from X5 project download site (https://www.npmjs.com/package/cordova-plugin-x5-webview) and build for both X86 and ARM architectures.
