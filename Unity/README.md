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

### 2. Simple Login Screen

If the Device ID is empty, please implement and display a simple login screen similar to this with a button that redirects to the XLoad App. The package name of XLoad App is com.xload.android. Don’t forget to use com.xload.android.debug for the development build.


### 3. Login to XLoad

Users will login or register on the XLoad app.

### 4. Login using XLD Endpoints

Call [**Authentication a User**](https://github.com/XLDTechLabs/XLD-Endpoints#2-authenticating-a-user) once the user returns to your game.
