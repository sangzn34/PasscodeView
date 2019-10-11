# PasscodeView 
[![](https://jitpack.io/v/sangzn34/PasscodeView.svg)](https://jitpack.io/#sangzn34/PasscodeView)

An Passcode view view for Android.
 

<div style="display:flex" >
 <img src="https://github.com/hanks-zyh/PasscodeView/raw/master/screenshot/demo1.png" width="220px" style="margin: 20px;">
 <img src="https://github.com/hanks-zyh/PasscodeView/blob/master/screenshot/demo2.png" width="220px" style="margin: 20px;">
 <img src="https://github.com/hanks-zyh/PasscodeView/raw/master/screenshot/demo.gif" width="220px" style="margin: 20px;">
</div>

## Usage

```gradle
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

```gradle
dependencies {
    implementation 'com.github.sangzn34:PasscodeView:1.0.3'
}
```

```xml
<com.hanks.passcodeview.PasscodeView
    android:id="@+id/passcodeView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#222222"
    app:firstInputTip="Enter a passcode of 5 digits "
    app:correctStateColor="#71bb4d"
    app:wrongStateColor="#ea2b46"
    app:normalStateColor="#ffffff"
    app:numberTextColor="#222222"
    app:passcodeLength="5"
    app:passcodeViewType="set_passcode"/>
```
### What new in  this version
```java
.setIsAutoClear(true)
.setIsAutoNext(true)
```

```java
passcodeView
        .setPasscodeLength(4)
        .setLocalPasscode("5555")
        .setIsAutoClear(true)
        .setIsAutoNext(true)
        .setListener(new PasscodeView.PasscodeViewListener() {
            @Override
            public void onFail(String wrongNumber) {
                Toast.makeText(getApplication(),"Wrong!!",Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onSuccess(String number) {
                Toast.makeText(getApplication(), "finish", Toast.LENGTH_SHORT).show();
            }
});
```
### 0.1.4

You can custom action numberOK and change drawable.
```java
passcodeView
        .setPasscodeLength(4)
        .setLocalPasscode("5555")
        .setIsAutoClear(true)
        .setIsAutoNext(true)
        .setOnClickAction(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(PasscodeActivity4.this, "Custom Click Action!!", Toast.LENGTH_LONG).show();
            }
        })
        .setListener(new PasscodeView.PasscodeViewListener() {
            @Override
            public void onFail(String wrongNumber) {
                Toast.makeText(getApplication(),"Wrong!!",Toast.LENGTH_SHORT).show();
            }
            @Override
            public void onSuccess(String number) {
                Toast.makeText(getApplication(), "finish", Toast.LENGTH_SHORT).show();
                onBackPressed();
            }
    });
```

```xml
app:extentActionDrawable="@drawable/ic_fingerprint_black_24dp"
```
or
```xml
app:isAddFingerScan="true"
```

## License

```
Copyright 2017 hanks

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
