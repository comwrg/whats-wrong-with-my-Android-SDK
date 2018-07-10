# whats-wrong-with-my-Android-SDK

## ddms 打开一片空白， macOS
https://bbs.csdn.net/topics/392291968   
Uninstall: https://docs.oracle.com/javase/8/docs/technotes/guides/install/mac_jdk.html 最下面   
8u144: http://download.oracle.com/otn/java/jdk/8u144-b01/090f390dda5b47b9b721c7dfaa008135/jdk-8u144-macosx-x64.dmg

## 错误: -source 1.7 中不支持 lambda 表达式 (请使用 -source 8 或更高版本以启用 lambda 表达式)
```

android {
    compileSdkVersion 26
    buildToolsVersion "27.0.3"
    defaultConfig {
        applicationId "me.wrg.autoconnect"
        minSdkVersion 21
        targetSdkVersion 26
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
+       jackOptions {
+           enabled true
+       }
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
    
+   compileOptions {
+       sourceCompatibility JavaVersion.VERSION_1_8
+       targetCompatibility JavaVersion.VERSION_1_8
+   }
    
}
```

## ddms 连接真机，不显示进程问题
需要在应用中开启debug
