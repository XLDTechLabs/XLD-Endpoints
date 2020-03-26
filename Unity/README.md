# XLD Endpoints Unity

### 1. Check for Device ID

Download the **XLDLogin.unitypackage** and import it on your project. You can now check if the device is logged in on XLD using this code:

```
XLDLogin.Instance.GetDeviceId()
```

You'll need to add this to AndroidManifest.xml

```
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
<manifest>
  <application
    android:requestLegacyExternalStorage="true">
  </application>
</manifest>
```
