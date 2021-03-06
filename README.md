### Titanium Firebase Module for Android

## Titanium Studio
Compile the module into your titanium project. From Titanium Studio, in the app explorer,  Click "Publish" and "Package Android Module". This will compile and package into your Titanium Project.

## Manual Install
Just unzip the dist/com.mlabieniec.ti.firebase-android-0.0.1.zip to your modules/android/ folder, and select it (or add it to) from the available modules in your tiapp.xml.

This is a native module for communicating with Firebase. It allows you to listen for change events on firebase collections. This is a work in progress and offers minimal functionality right now. Soon we will have an alloy sync adapter that abstracts the Firebase logic so that you can work with standard models in alloy.

    var firebase = require('com.mlabieniec.ti.firebase');
    firebase.FIREBASE_URL = "https://YOUR_DOMAIN.firebaseIO.com";
    firebase.FIREBASE_AUTH = "YOUR_API_KEY";
    firebase.init(ref);
    
"ref" is the name of your firebase collection you want to listen to changes for, i.e. You would reference it on your firebase like: https://myfirebase.firebaseio.com/ref. You can then listen for property changes on collections in firebase with a propertyChangeHandler:
    
    firebase.addEventListener("propertyChange",propertyChangeHandler);
    
    function propertyChangeHandler(e) {
    	   alert('Property Change\nproperty: ' + e.property + '\noldValue: ' + e.oldValue + '\nnewValue: ' + e.newValue);
    }
    
