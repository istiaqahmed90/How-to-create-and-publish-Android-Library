# Publish your library online
1. release your project on github.
![alt text](https://github.com/istiaqahmed90/How-to-create-and-publish-Android-Library/blob/master/release.png)

2. publish on 
https://jitpack.io/
![alt text](https://github.com/istiaqahmed90/How-to-create-and-publish-Android-Library/blob/master/jit.png)

3. Add it in your root build.gradle at the end of repositories:
```java
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}

```

4. add below line to your gradle app
implementation 'com.github.istiaqahmed90:make_lib:1.0'




gradle app file look like
```java
apply plugin: 'com.android.application'

android {
    compileSdkVersion 29
    buildToolsVersion "29.0.3"
    defaultConfig {
        applicationId "com.example.publishlib"
        minSdkVersion 15
        targetSdkVersion 29
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
}

dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation 'androidx.appcompat:appcompat:1.1.0'
    implementation 'androidx.constraintlayout:constraintlayout:1.1.3'
    implementation 'com.google.android.material:material:1.1.0'
    implementation 'com.github.istiaqahmed90:make_lib:1.0'
    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'androidx.test.ext:junit:1.1.0'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.2.0'
}


```

