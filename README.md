All .md
| [2nd repo](https://github.com/Engineering-college-btech/custom-video-player/blob/main/2nd%20repository.md) |
|---
| [Security](https://github.com/Engineering-college-btech/custom-video-player/blob/main/Security.md) |
| [Style](https://github.com/Engineering-college-btech/custom-video-player/blob/main/Style.md) |

# freecad_app 

| [Download FreeCAD old-App](https://github.com/Engineering-college-btech/custom-video-player/releases/tag/freecad) |
|---

|🍭 [Downlod-app](https://akashdip2001.github.io/freecad_app/app_download.html) 🍭|🐥 [old app interface](https://akashdip2001.github.io/freecad_app/) 🐥|❌ [New app interface](https://github.com/Engineering-college-btech/custom-video-player/blob/main/Security.md) ❌|
|-------------------- |-------------------- |-------------------- |

![webapp dev (2)](https://github.com/akashdip2001/freecad_app/assets/81384987/beec1827-4afe-4394-9394-941db53c43db)
![webapp dev (3)](https://github.com/akashdip2001/freecad_app/assets/81384987/979c980e-77e1-432a-b69a-2da4e18f22ad)

# Android studio code

# activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <WebView
        android:id="@+id/webView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</LinearLayout>
```
# MainActivity.java
```java
package com.example.cadpro;

import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;
import android.webkit.WebSettings;
import android.webkit.WebView;

public class MainActivity extends AppCompatActivity {
    private WebView webView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        webView = findViewById(R.id.webView);
        WebSettings webSettings = webView.getSettings();
        webSettings.setJavaScriptEnabled(true); // Enable JavaScript if your site requires it

        // Load the URL into the WebView
        webView.loadUrl(getString(R.string.webview_url));
    }
}
```
# AndroidManifes.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.CADPro"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        tools:targetApi="31">

        <activity
            android:name=".MainActivity"
            android:screenOrientation="portrait"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

    </application>

</manifest>
```
# Strings.xml
```xml
<resources>
    <string name="app_name">CAD pro</string>
    <string name="webview_url">https://akashdip2001.github.io/freecad_app/</string>
</resources>
```

<div style="display: flex; justify-content: space-between;">
    <img src="https://github.com/akashdip2001/freecad_app/assets/81384987/ce9f6d8e-965e-4aed-970e-28d0fa2babb7" width="30%">
     <img src="https://github.com/akashdip2001/freecad_app/assets/81384987/2054e341-77be-413b-aa33-58fa735e574e" width="30%">
     <img src="https://github.com/akashdip2001/freecad_app/assets/81384987/7dd4bb0e-4821-4e26-be0b-a5034561bdcb" width="30%">
   
</div>

<div style="display: flex; justify-content: space-between;">
    <img src="https://github.com/akashdip2001/freecad_app/assets/81384987/9c663d1a-3a53-4d47-bdd8-a933bc26001d" alt="akashdipmahapatra" style="border-radius: 50%;" width="48%">
    <img src="https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/e938ce6d-b808-4d66-a5f2-f64b8d25a59d" style="border-radius: 50%;" width="48%">
</div>

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">
❌❌❌ ⬇️⬇️⬇️

# Update - New app (16/01/24)
# This app finnaly not work 
# The <scripts> run in the app - But the Web-page not appears - Complete Black

```java
package com.akashdipmahapatra.freecad;

import android.content.Intent;
import android.graphics.Color;
import android.graphics.drawable.ColorDrawable;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.webkit.WebChromeClient;
import android.webkit.WebResourceRequest;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private WebView webView;
    private Button refreshButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Disable screen rotation
        setRequestedOrientation(android.content.pm.ActivityInfo.SCREEN_ORIENTATION_PORTRAIT);

        // Initialize WebView and refresh button
        webView = findViewById(R.id.webView);
        refreshButton = findViewById(R.id.refreshButton);

        // Set up WebView
        setupWebView();

        // Set up refresh button click listener
        refreshButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                webView.reload();
            }
        });
    }

    private void setupWebView() {
        WebSettings webSettings = webView.getSettings();
        webSettings.setJavaScriptEnabled(true);

        webView.setWebViewClient(new WebViewClient() {
            @Override
            public boolean shouldOverrideUrlLoading(WebView view, WebResourceRequest request) {
                String url = request.getUrl().toString();

                // Check if the link is the YouTube channel link
                if (url.equals("https://www.youtube.com/channel/UCxvmp634YDc41xCWOdvWqoQ?sub_confirmation=1")) {
                    // Open YouTube link in external browser
                    startActivity(new Intent(Intent.ACTION_VIEW, Uri.parse(url)));
                    return true;
                }

                // Load other links inside the WebView
                view.loadUrl(url);
                return true;
            }
        });

        webView.setWebChromeClient(new WebChromeClient() {
            @Override
            public void onReceivedTitle(WebView view, String title) {
                super.onReceivedTitle(view, title);
                // You can use the title to dynamically change the app color
                int color = Color.parseColor("#FF5733"); // Example color
                updateAppColor(color);
            }
        });

        // Load an initial URL
        webView.loadUrl("https://example.com");
    }

    private void updateAppColor(int color) {
        // Update the app color dynamically
        getWindow().setStatusBarColor(color);
        getSupportActionBar().setBackgroundDrawable(new ColorDrawable(color));
    }
}
```

```xml
<!-- res/layout/activity_main.xml -->
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <WebView
        android:id="@+id/webView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_above="@+id/toolbar" />

    <Button
        android:id="@+id/refreshButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:layout_margin="16dp"
        android:text="Refresh" />

</RelativeLayout>
```

### 2. Create `AndroidManifest.xml`:

If the `AndroidManifest.xml` file doesn't exist, you can create it manually. In the `app` module, navigate to the `src/main` directory and create a new XML file named `AndroidManifest.xml`. Below is a basic example:

```xml
<!-- app/src/main/AndroidManifest.xml -->
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.akashdipmahapatra.freecad">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">

        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

    </application>

</manifest>
```

# app logo

![freecad_img](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/e938ce6d-b808-4d66-a5f2-f64b8d25a59d)

# final 

![1](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/347ca51b-8adb-4d62-9f5f-bc1a89102ea5)

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    package="com.akashdipmahapatra.freecad">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="freecad"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Freecad"
        tools:targetApi="31">

        <activity android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

    </application>

</manifest>

```
![Screenshot (39)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/20628d85-719a-4589-8911-f0e432d89b5c)
![Screenshot (38)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/a1ec15ac-fe9e-407c-92c4-47156dc4c426)
```java
package com.akashdipmahapatra.freecad;

import android.content.Intent;
import android.graphics.Color;
import android.graphics.drawable.ColorDrawable; // Import the ColorDrawable class
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.webkit.WebChromeClient;
import android.webkit.WebResourceRequest;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private WebView webView;
    private Button refreshButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Disable screen rotation
        setRequestedOrientation(android.content.pm.ActivityInfo.SCREEN_ORIENTATION_PORTRAIT);

        // Initialize WebView and refresh button
        webView = findViewById(R.id.webView);
        refreshButton = findViewById(R.id.refreshButton);

        // Set up WebView
        setupWebView();

        // Set up refresh button click listener
        refreshButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                webView.reload();
            }
        });
    }

    private void setupWebView() {
        WebSettings webSettings = webView.getSettings();
        webSettings.setJavaScriptEnabled(true);

        webView.setWebViewClient(new WebViewClient() {
            @Override
            public boolean shouldOverrideUrlLoading(WebView view, WebResourceRequest request) {
                String url = request.getUrl().toString();

                // Check if the link is the YouTube channel link
                if (url.equals("https://www.youtube.com/channel/UCxvmp634YDc41xCWOdvWqoQ?sub_confirmation=1")) {
                    // Open YouTube link in external browser
                    startActivity(new Intent(Intent.ACTION_VIEW, Uri.parse(url)));
                    return true;
                }

                // Load other links inside the WebView
                view.loadUrl(url);
                return true;
            }
        });

        webView.setWebChromeClient(new WebChromeClient() {
            @Override
            public void onReceivedTitle(WebView view, String title) {
                super.onReceivedTitle(view, title);
                // You can use the title to dynamically change the app color
                int color = Color.parseColor("#FF5733"); // Example color
                updateAppColor(color);
            }
        });

        // Load an initial URL
        webView.loadUrl("https://tiny-hamster-b2a057.netlify.app");
    }

    private void updateAppColor(int color) {
        // Update the app color dynamically
        getWindow().setStatusBarColor(color);
        getSupportActionBar().setBackgroundDrawable(new ColorDrawable(color));
    }

    public void onRefreshButtonClick(View view) {
        webView.reload();
    }
}

```
![Screenshot (40)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/f197c11f-53b9-4f98-9faf-93106d1f8bce)
```xml
<!-- res/layout/activity_main.xml -->
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <WebView
        android:id="@+id/webView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_above="@+id/refreshButton" />


    <Button
        android:id="@+id/refreshButton"
        android:layout_width="48dp"
        android:layout_height="48dp"
        android:layout_alignParentEnd="true"
        android:layout_margin="16dp"
        android:background="@drawable/round_button"
        android:drawableTop="@drawable/ic_refresh"
        android:onClick="onRefreshButtonClick"
        android:contentDescription="Refresh Button"
        android:text=""
        android:textColor="@android:color/transparent" />

</RelativeLayout>

```
![Screenshot (41)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/70276f6d-de9d-4a2e-b097-4e096329a5a1)
```xml
<!-- res/drawable/round_button.xml -->
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="oval">
    <solid android:color="#80000000" /> <!-- Transparent gray color -->
</shape>

```
![Screenshot (42)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/51762b4f-ff23-41b5-97bc-05a568a0cb47)
```xml
<!-- res/drawable/ic_refresh.xml -->
<vector xmlns:android="http://schemas.android.com/apk/res/android"
    android:width="24dp"
    android:height="24dp"
    android:viewportWidth="24.0"
    android:viewportHeight="24.0">
    <path
        android:fillColor="#FFFFFF"
        android:pathData="M8,4V1L4,5L8,9V6C12.41,6 16,9.59 16,14C16,18.41 12.41,22 8,22C3.59,22 0,18.41 0,14C0,9.59 3.59,6 8,6H9V9L12,6L9,3V6H8C5.79,6 4,7.79 4,10C4,12.21 5.79,14 8,14C10.21,14 12,12.21 12,10V4H8Z" />
</vector>

```
![Screenshot (43)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/2c4693c8-99e4-4fe7-8877-e570234f2299)
```kts
plugins {
    id("com.android.application")
}

android {
    namespace = "com.akashdipmahapatra.freecad"
    compileSdk = 34

    defaultConfig {
        applicationId = "com.akashdipmahapatra.freecad"
        minSdk = 29
        targetSdk = 34
        versionCode = 1
        versionName = "1.0"

        testInstrumentationRunner = "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            isMinifyEnabled = false
            proguardFiles(
                getDefaultProguardFile("proguard-android-optimize.txt"),
                "proguard-rules.pro"
            )
        }
    }
    compileOptions {
        sourceCompatibility = JavaVersion.VERSION_1_8
        targetCompatibility = JavaVersion.VERSION_1_8
    }
}

dependencies {

    implementation("androidx.appcompat:appcompat:1.6.1")
    implementation("com.google.android.material:material:1.10.0")
    testImplementation("junit:junit:4.13.2")
    androidTestImplementation("androidx.test.ext:junit:1.1.5")
    androidTestImplementation("androidx.test.espresso:espresso-core:3.5.1")
}
```

---
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">
✅✅✅ ✔️✔️✔️

# Now Creat from begning (17/01/24)

# MainActivity.java

```java
package com.akashdipmahapatra.freecad;

import android.os.Bundle;
import android.webkit.WebChromeClient;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.webkit.WebViewClient;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private WebView webView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        webView = findViewById(R.id.webView);
        setupWebView();

        String url = "https://tiny-hamster-b2a057.netlify.app";
        webView.loadUrl(url);
    }

    private void setupWebView() {
        WebSettings webSettings = webView.getSettings();
        webSettings.setJavaScriptEnabled(true);
        webView.setWebViewClient(new WebViewClient());

        // Allow video full screen
        webView.setWebChromeClient(new WebChromeClient());
    }

    // Handle back button press
    @Override
    public void onBackPressed() {
        if (webView.canGoBack()) {
            webView.goBack();
        } else {
            super.onBackPressed();
        }
    }
}
```
# activity_main.xml
![Screenshot (45)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/b5726f3c-328a-46c9-98d4-22c5aa6d9793)
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <WebView
        android:id="@+id/webView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</RelativeLayout>
```
# AndroidManifest.xml
![Screenshot (46)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/e7e417a1-52ae-4aed-9b3b-582bd86415a9)
```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.akashdipmahapatra.freecad">

    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="freecad"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">

        <activity android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

    </application>

</manifest>
```
# res/values/styles.xml
![Screenshot (47)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/bb9d2262-9867-4826-a429-b7e17235b56d)
![Screenshot (48)](https://github.com/Engineering-college-btech/custom-video-player/assets/81384987/d2b14779-0bb8-4efc-bbb9-e15ca52c0f23)

```xml
<resources>

    <!-- Base application theme -->
    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
        <!-- Add other customizations if needed -->
    </style>

</resources>
```
```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="purple_200">#FFBB86FC</color>
    <color name="purple_500">#FF6200EE</color>
    <color name="purple_700">#FF3700B3</color>
    <color name="teal_200">#FF03DAC5</color>
    <color name="teal_700">#FF018786</color>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name="colorPrimary">#3F51B5</color>
    <color name="colorPrimaryDark">#303F9F</color>
    <color name="colorAccent">#FF4081</color>

</resources>
```
---
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">

# Update - Subscribe button - YouTube app 

```java
private class MyWebViewClient extends WebViewClient {
    @Override
    public boolean shouldOverrideUrlLoading(WebView view, WebResourceRequest request) {
        Uri url = request.getUrl();
        if (isSocialMediaUrl(url.toString())) {
            // Open social media links in the browser or respective apps
            openExternalLink(url.toString());
            return true; // Indicates that the WebView should not handle the URL
        } else {
            // Continue loading other URLs in the WebView
            return false;
        }
    }

    private boolean isSocialMediaUrl(String url) {
        return url.startsWith("https://www.youtube.com/channel/") ||
               url.startsWith("https://www.facebook.com/") ||
               url.startsWith("https://www.instagram.com/") ||
               url.startsWith("https://www.linkedin.com/");
    }

    private void openExternalLink(String url) {
        Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
        startActivity(intent);
    }
}
```
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">

# Update - all error fix ( still - White Screen Problam )

```java
package com.akashdipmahapatra.freecad;

import android.content.Intent;
import android.content.pm.ActivityInfo;
import android.content.res.Configuration;
import android.graphics.Bitmap;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.webkit.WebChromeClient;
import android.webkit.WebResourceRequest;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import android.widget.FrameLayout;
import android.widget.ProgressBar;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private WebView webView;
    private FrameLayout frameLayout;
    private ProgressBar progressBar; // Add this line for ProgressBar

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        webView = findViewById(R.id.webView);
        frameLayout = findViewById(R.id.frameLayout); // Initialize frameLayout
        progressBar = findViewById(R.id.progressBar); // Initialize progressBar

        setupWebView();

        String url = "https://tiny-hamster-b2a057.netlify.app";
        webView.loadUrl(url);
    }

    private void setupWebView() {
        WebSettings webSettings = webView.getSettings();
        webSettings.setJavaScriptEnabled(true);
        webView.setWebViewClient(new MyWebViewClient());
        webView.setWebChromeClient(new MyWebChromeClient());

        // Block screen rotation except during video fullscreen
        setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_PORTRAIT);
    }

    private class MyWebViewClient extends WebViewClient {
        @Override
        public boolean shouldOverrideUrlLoading(WebView view, WebResourceRequest request) {
            Uri url = request.getUrl();
            if (isSocialMediaUrl(url.toString())) {
                // Open social media links in the browser or respective apps
                openExternalLink(url.toString());
                return true; // Indicates that the WebView should not handle the URL
            } else {
                // Continue loading other URLs in the WebView
                return false;
            }
        }

        @Override
        public void onPageStarted(WebView view, String url, Bitmap favicon) {
            super.onPageStarted(view, url, favicon);
            // Show ProgressBar when page starts loading
            progressBar.setVisibility(View.VISIBLE);
        }

        @Override
        public void onPageFinished(WebView view, String url) {
            super.onPageFinished(view, url);
            // Hide ProgressBar when page finishes loading
            progressBar.setVisibility(View.GONE);
        }

        private boolean isSocialMediaUrl(String url) {
            return url.startsWith("https://www.youtube.com/channel/") ||
                    url.startsWith("https://www.facebook.com/") ||
                    url.startsWith("https://www.instagram.com/") ||
                    url.startsWith("https://www.linkedin.com/");
        }

        private void openExternalLink(String url) {
            Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
            startActivity(intent);
        }
    }

    private class MyWebChromeClient extends WebChromeClient {

        private View mCustomView;
        private CustomViewCallback mCustomViewCallback;

        // Override to handle entering fullscreen
        @Override
        public void onShowCustomView(View view, CustomViewCallback callback) {
            if (mCustomView != null) {
                callback.onCustomViewHidden();
                return;
            }

            mCustomView = view;
            mCustomViewCallback = callback;

            setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_LANDSCAPE);
            webView.setVisibility(View.GONE);
            frameLayout.addView(view);
            frameLayout.setVisibility(View.VISIBLE);

            // Hide ActionBar when entering fullscreen
            getSupportActionBar().hide();
        }

        // Override to handle exiting fullscreen
        @Override
        public void onHideCustomView() {
            if (mCustomView == null) {
                return;
            }

            setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_PORTRAIT);
            webView.setVisibility(View.VISIBLE);
            frameLayout.removeView(mCustomView);
            frameLayout.setVisibility(View.GONE);

            // Show ActionBar when exiting fullscreen
            getSupportActionBar().show();

            mCustomView = null;
            mCustomViewCallback.onCustomViewHidden();
        }
    }

    // Handle back button press
    @Override
    public void onBackPressed() {
        if (webView.canGoBack()) {
            webView.goBack();
        } else {
            // If no page to go back, handle as needed
            super.onBackPressed();
        }
    }

    @Override
    public void onConfigurationChanged(Configuration newConfig) {
        super.onConfigurationChanged(newConfig);
        // Handle configuration changes if necessary
    }
}
```
activity_main,xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <FrameLayout
        android:id="@+id/frameLayout"
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <WebView
            android:id="@+id/webView"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />

        <!-- Add a ProgressBar to show loading progress -->
        <ProgressBar
            android:id="@+id/progressBar"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center" />
    </FrameLayout>

</RelativeLayout>
```
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">

[final app](https://github.com/Engineering-college-btech/custom-video-player/blob/main/app.md)
