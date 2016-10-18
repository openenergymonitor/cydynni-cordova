
## Cyd Ynni Mobile App Cordova Build


[![Build Status](https://travis-ci.org/openenergymonitor/cydynni-cordova.svg?branch=master)](https://travis-ci.org/openenergymonitor/cydynni-cordova)

Cordova build files for [Cyd Ynni web application](https://github.com/trystanlea/cydynni).

Thanks to @davehun

### Install Cordova

`sudo npm install cordova -g`

Add path to Android SDK variable

`echo 'export ANDROID_HOME=~/Android/Sdk' >> ~/.bashrc`

## Android Build

cd cydynni-cordova

If exisits remove platforms folder to start a fresh build

`rm -rf platforms`

### Debug apk

```
cordova prepare
cordova build android
```

### Release apk

```
cordova prepare
cordova build android --release
```

### Sign APK

`jarsigner -verbose -keystore android.jks platforms/android/build/outputs/apk/android-release-unsigned.apk "cyd ynni hydro"`

Where android.jks is our signing key

### Zip Align

`$ANDROID_HOME/build-tools/23.0.3/./zipalign -v 4 platforms/android/build/outputs/apk/android-release-unsigned.apk platforms/android/build/outputs/apk/android-release-signed-aligned.apk`

APK is now ready to publish :-)

***

## Licence

This software is available under the GNU GPL V3 license
