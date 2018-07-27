![Onmobile: Logo](http://t0.gstatic.com/images?q=tbn:ANd9GcQ7a6C5baa2f_3KA2zVpouH29tMGgRfcCn1PGuubySgbFbKuMxg)

# Wrapper Game Onmo SDK

Wrapper Game Onmo SDK is library to access and communicate with UGames Store Android applications.
SDK provides required information through callback methods to Wraper games.

just start your app and complete the below integration set-up given instructions.


## Set-up


 *   Step 1. Add the JitPack repository to your build file

    Add it in your root build.gradle at the end of repositories:
```groovy
allprojects {
    repositories {
        ...
        maven { url 'https://www.jitpack.io' }
    }
}
```


 *   Step 2. Add the dependency in app build.gradle

```groovy
implementation 'com.github.srinivasvadde:OnmoWGameSDK:1.17'
```


### Usage

 Integrating with Wrapper Game Onmo SDK is simple and straightforward access to Wrapper Game applications.
There is a simple initialization step required in your `MainActivity` or `Application class`:

```java

    public class MainActivity extends AppCompatActivity {
      public void onCreate() {
        super.onCreate();
        //init the SDK
        OnmoWGSDK.newInitializer(mContext);
      }
    }
```

### Accessing SDK methods
To Access any of Wrapper Game Onmo SDK method is allowed through IWGameSession interface, example code given below :

```java
IWGameSession mWGSession = OnmoWGSDK.newInitializer(mContext)
                              .build();
```


#### Authenticating with accesses token

we will share you access token to use the OnmoWGSDK

```java
//Basic authentication
IWGameSession mWGSession = OnmoWGSDK.newInitializer(mContext)
                              .build(o6a-PfU-Phc-3tq);
```

#### Example - Getting User ID

```java

        mWGSession.getUserId(new IResponseHandler<String>() {
            @Override
            public void handleResponse(String aUserId) {
                // wrapper game get the aUserId in callback result
            }

            @Override
            public void handleException(SDKException exception) {
                // in case any error it will come here
            }
        });

```

#### Example - Getting User subscription status

```java

         mWGSession.isUserActive(new IResponseHandler<Boolean>() {
                @Override
                public void handleResponse(Boolean config) {
                    // if the user is active for any subscription pack will return true other wise false.
                }

                @Override
                public void handleException(SDKException exception) {
                     // in case any error it will come here
                }
          });

```



See the [`WGOnmoSDKDemoApp`](https://github.com/srinivasvadde/WGOnmoSDKDemoApp) for the details use of SDK methods and integration.



#### Copyright

##### ©2018 OnMobile Global Limited All Rights Reserved.