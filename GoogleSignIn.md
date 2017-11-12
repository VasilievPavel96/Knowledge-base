# Google sign in

## Get configuration file from here [](https://developers.google.com/mobile/add?platform=android&cntapi=signin&cnturl=https:%2F%2Fdevelopers.google.com%2Fidentity%2Fsign-in%2Fandroid%2Fsign-in%3Fconfigured%3Dtrue&cntlbl=Continue%20Adding%20Sign-In)
Copy the google-services.json file you just downloaded into the app/ folder
## Add the Google Services plugin
1. Add the dependency to your project-level build.gradle
`classpath 'com.google.gms:google-services:3.1.0'`
2. Add the plugin to your app-level build.gradle
`apply plugin: 'com.google.gms.google-services'
