# NewSDKAndroidDemo

#### Software Architecture:
Software architecture description<br />
1.Lock Operate Api:TTLockClient<br />
2.Lock firmware update Api:LockDfuClient<br />
3.Gateway Api:GatewayClient<br />

#### IDE
Android Studio

#### Minimum SDK Version
18

### Import
```
implementation 'com.tongtonglock:ttlock:3.0.6'
```

#### add permission in manifest
```
<uses-permission android:name="android.permission.BLUETOOTH" />
<uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```
### Init SDK

#### 1)Before call sdk api,make sure bluetooth is enabled
#### 2)Init SDK
```
TTLockClient.getDefault().prepareBTService(getApplicationContext());
```

#### 3)Use api
```
TTLockClient.getDefault().startScanLock(new ScanLockCallback() {
    @Override
    public void onScanLockSuccess(ExtendedBluetoothDevice device) {

    }
});
```
### Reset SDK
#### When Activity finished,you should close SDK service
```
TTLockClient.getDefault().stopBTService();
```

