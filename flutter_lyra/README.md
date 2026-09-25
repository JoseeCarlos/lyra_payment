# Zencillo Lyra Flutter integration

Internal Flutter federated plugin maintained by Zencillo. The Dart package name
remains `flutter_lyra` for compatibility with the existing application.

## Installation

### Android

Prerequisites:

- In your `android/app/build.gradle`, update your `minSdkVersion` in your default config :

```gradle
defaultConfig {
        // others configs
        minSdkVersion 21
    }
```

- If you are using `FlutterActivity` directly, change it to
  `FlutterFragmentActivity` in your `AndroidManifest.xml`.
- If you are using a custom activity, update your `MainActivity.java`:

  ```java
  import io.flutter.embedding.android.FlutterFragmentActivity;

  public class MainActivity extends FlutterFragmentActivity {
      // ...
  }
  ```

  or `MainActivity.kt`:

  ```kotlin
  import io.flutter.embedding.android.FlutterFragmentActivity

  class MainActivity: FlutterFragmentActivity() {
      // ...
  }
  ```

  to inherit from `FlutterFragmentActivity`.

- Use a theme that inherits MaterialTheme for the Android theme to apply to
  the FlutterFragmentActivity as soon as the Android process has started

  For example :

  - In your `android/app/build.gradle`, you can add this dependency

  ```gradle
  dependencies {
    implementation "com.google.android.material:material:1.5.0"
    // your others dependencies
  }
  ```

  - In your `android/app/src/main/res/values/styles.xml`

    ```xml
    <!-- Theme applied to the Android Window as soon as the process has started.
            This theme determines the color of the Android Window while your
            Flutter UI initializes, as well as behind your Flutter UI while its
            running.

            This Theme is only used starting with V2 of Flutter's Android embedding. -->
        <style name="NormalTheme" parent="@style/Theme.Material3.Light.NoActionBar">
            <!-- Or any other material theme that you want -->
            <item name="android:windowBackground">?android:colorBackground</item>
        </style>
    ```

    Don't forget to change it as well in your `android/app/src/main/res/values-night/styles.xml` if you need to

### iOS

Prerequisites:

- In your `ios/Podfile`, update your ios sdk version :

```rb
platform :ios, '15.1'
```

## About Lyra

This sdk is the flutter interface implementation of the [android](https://github.com/lyra/android-sdk) and [ios](https://github.com/lyra/ios-sdk) sdks of Lyra

If you want more informations about Lyra, here is their [website](https://payzen.io/fr-FR/)

## Ownership and third-party dependencies

This package is maintained internally by Zencillo for Zencillo applications.
Lyra, PayZen, and their SDKs are third-party products and their trademarks
remain property of their respective owners.
