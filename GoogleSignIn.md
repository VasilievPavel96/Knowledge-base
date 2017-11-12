# Google sign in

## Get configuration file from here [](https://developers.google.com/mobile/add?platform=android&cntapi=signin&cnturl=https:%2F%2Fdevelopers.google.com%2Fidentity%2Fsign-in%2Fandroid%2Fsign-in%3Fconfigured%3Dtrue&cntlbl=Continue%20Adding%20Sign-In)
Copy the google-services.json file you just downloaded into the app/ folder
## Add dependencies to build.gradle
1. Add the dependency to your project-level build.gradle
`classpath 'com.google.gms:google-services:3.1.0'`
2. Add the plugin to your app-level build.gradle
`apply plugin: 'com.google.gms.google-services'`
3. Add play-services-auth library 
`'com.google.android.gms:play-services-auth:9.0.0'`
## Configure GoogleApiClient in onCreate of Activity
```kotlin
val gso = GoogleSignInOptions.Builder(GoogleSignInOptions.DEFAULT_SIGN_IN)
                .requestEmail()
                .build()
val googleApiClient = GoogleApiClient.Builder(this)
        .addApi(Auth.GOOGLE_SIGN_IN_API, gso)
        .build()
```
## Setup listeners on buttons
```kotlin
signInButton.setOnClickListener {
    val intent = Auth.GoogleSignInApi.getSignInIntent(googleApiClient)
    startActivityForResult(intent, RC_SIGN_IN)
}
signOutButton.setOnClickListener {
    Auth.GoogleSignInApi.signOut(googleApiClient).setResultCallback {
        if (it.isSuccess) {
            statusLabel.text = "not authorized"
        }
    }
}
```
## Handle result callback
```kotlin
override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {
    if (requestCode == RC_SIGN_IN) {
        val result = Auth.GoogleSignInApi.getSignInResultFromIntent(data)
        if (result.isSuccess) {
            val account = result.signInAccount;
            statusLabel.text = "authorized"
        }
    } else {
        super.onActivityResult(requestCode, resultCode, data)
    }
}
```