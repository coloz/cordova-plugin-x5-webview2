cordova-plugin-x5-webview2
====

本项目fork自[cordova-plugin-x5-webview](https://github.com/jeremyup/cordova-plugin-x5-webview)  
更新到最新的X5 SDK，并适配cordova-android 7.x  

## 使用方法  
```
cordova plugin add https://github.com/coloz/cordova-plugin-x5-webview2.git
```

在项目的MainActivity中添加:  

```java
import com.tencent.smtt.sdk.QbSdk;

QbSdk.PreInitCallback cb = new QbSdk.PreInitCallback() {

      @Override
      public void onViewInitFinished(boolean arg0) {
        // TODO Auto-generated method stub
        //x5內核初始化完成的回调，为true表示x5内核加载成功，否则表示x5内核加载失败，会自动切换到系统内核。
        Log.d("app", " onViewInitFinished is " + arg0);
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

## 已知问题  
1.切换到X5内核后，会导致cordova无法联机调试，android studio可调试  
