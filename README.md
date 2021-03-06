# rn-live

# Info
This library based [rtmp-rtsp-stream-client-java](https://github.com/pedroSG94/rtmp-rtsp-stream-client-java)
and [LFLiveKit](https://github.com/LaiFengiOS/LFLiveKit)

**Support iOS and Android**

## Add it to your project

Run `npm install --save rn-live`

### Android
1. Add the following lines to `android/settings.gradle`:
    ```gradle
    include ':rn-live'
    project(':rn-live').projectDir = new File(rootProject.projectDir, '../node_modules/rn-live/android')
    ```

2. Add the compile line to the dependencies in `android/app/build.gradle`:
    ```gradle
    dependencies {
        compile project(':rn-live')
    }
    ```

5. Add the required permissions in `AndroidManifest.xml`:
    ```xml
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>
        <uses-permission android:name="android.permission.RECORD_AUDIO" />
        <uses-permission android:name="android.permission.CAMERA" />
        <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
        <uses-feature android:name="android.hardware.camera" />
        <uses-feature android:name="android.hardware.camera2.full" />
        <uses-feature android:name="android.hardware.camera2.autofocus" />

    ```

6. Add the import and link the package in `MainApplication.java`:
    ```java
    import com.rnlive.RTMPPackage; // <-- add this import

    public class MainApplication extends Application implements ReactApplication {
        @Override
        protected List<ReactPackage> getPackages() {
            return Arrays.<ReactPackage>asList(
                new MainReactPackage(),
                new RTMPPackage() // <-- add this line
            );
        }
    }
    ```

### iOS

1. In the XCode's "Project navigator", right click on your project's Libraries folder ➜ `Add Files to <...>`
2. Go to `node_modules` ➜ `rn-live` ➜ `ios` ➜ select `RCTLFLiveKit.xcodeproj`
3. Add `libRCTLFLiveKit.a` to `Build Phases -> Link Binary With Libraries`
4. Go to General -> Embedded Binaries and add LFLiveKit.framework
5. Linked Frameworks and Libraries add LFLiveKit.framework
6. Compile and have fun

## Usage

```javascript
    <RNLive
        started={false} // start your stream
        cameraFronted={true} // camera front or back
        url="rtmp://xxx" // your rtmp publish url
        landscape={false} // landscape mode
        onReady={() => {}} // streaming ready
        onPending={() => {}} // streaming ready to start
        onStart={() => {}} // streaming start
        onError={() => {}} // straming error
        onStop={() => {}} // streaming stop
        />
```


### Options

option | iOS  | Android
------ | ---- | -------
cameraFronted | OK | OK
started | OK | OK
url | OK | OK
landscape | OK | -
onReady | OK | -
onPending | OK | -
onStart | OK | -
onStop | OK | -
onError | OK | -
videoEnabled | - | OK
audioEnabled | - | OK

# License
MIT
    https://www.npmjs.com/package/rn-live