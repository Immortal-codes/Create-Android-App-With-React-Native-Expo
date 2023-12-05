# Create-Android-App-With-React-Native-Expo


Creating APK for Android in React Native Expo Eas Build [Updated 2023]
Post author
By Furquan Ul Haque
Post date
May 12, 2023
Categories
In React Native
Creating APK for android in React Native Expo Eas Build is very easy. Some times you would want to create an apk for either local installation or testing purpose. In that case you don’t want to publish it on Google Play Store. That’s why in this tutorial, we will take a look at how to create apk in expo react native for manual installation in android.

Step 1: Install Expo CLI
Run the following command to install the expo CLI


npm install --global expo-cli eas-cli
Then you van check the version of the installed Expo CLI by using the following command:

 expo -V
Step 2: Create React Native Expo Project
First step is to create React Native Project in Expo. We are not going over how to create one in this tutorial. However, you can visit this page on how to create a react Native project from start.


Also note that you must be logged in on your expo account on browser as well as in expo command terminal.
Step 3 Create eas.json file in React Native project
It seems like by default, expo eas build will create a build for play store, which is an aab file. But we need apk file. So you need to create eas.json file in the root directory of your project (same path as your App.js). By default this file is not there, so you need to create one. And add the following code in it:


{
  "build": {
    "preview": {
      "android": {
        "buildType": "apk"
      }
    },
    "preview2": {
      "android": {
        "gradleCommand": ":app:assembleRelease"
      }
    },
    "preview3": {
      "developmentClient": true
    },
    "production": {}
  }
}

For detailed documentation about Eas Build, click here

Step 4: Creating APK for Android in React Native Expo
The last step is to queue your build in expo. And you do that by the following command in your terminal or command prompt:


eas build -p android --profile preview
Then you have to wait for the bundle to complete its build.

Step 5: Installation on Android Device
Once the build is completed, you can download your APK file directly from your expo dashboard and install manually in any of your android device as shown below. Hope it helps and now you are equipped in creating APK for Android in React Native Expo!

