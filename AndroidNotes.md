# Android Notes

### Tips for using EventBus
1. When dealing with Android lifecycle with eventbus, make sure subscribers are registered at the earliest possible stage and any calls follow after.

### Broadcast Receivers
**Implementation steps**

1. Create a class to implement `BroadcastReceiver` and write the logic for handling the broadcast.
2. Register the receiver in `AndroidManifest.xml` and specify the permission it must have in order to listen to the said broadcast.

 ```xml
<receiver android:name="MyPhoneReceiver" >
        <intent-filter>
            <action android:name="android.intent.action.PHONE_STATE" >
            </action>
        </intent-filter>
    </receiver>
 ```
3. Give the app the necessary permissions to enable receiving the said broadcast.

**Tip**
* In order to send local broadcasts, create an intent that points to the required broadcast.

### Security on Android

**Data Tansfer Security**
 - HTTPS in iteself is good enough to ensure that the data transfer can not be snooped on.
 - Additional use of ProtocolBuffers can further improve security as its binary and the schema is only known to the server and the client.
 - Use Auth token based server request mechanism to ensure autherised API access.
 
**Data Storage Security**
- Store the username & password only in [Account Manager](https://developer.android.com/reference/android/accounts/AccountManager.html) as its secured and access is restricted to the app.
- Data stored in database should in encrypted. For SQLlite use [SQLCipher](https://guardianproject.info/code/sqlcipher/). [Realm](https://realm.io/docs/java/latest/#encryption) has in build support for AES-256 level encryption. Both need an encryption key to encrypt and decrypt data at run time.
- Never store the encryption key on the device. Always generate one at run time and keep in memory.
- Use the [KeyStore](https://developer.android.com/training/articles/keystore.html#GeneratingANewPrivateKey) to generate an encryption key by giving it the following base data at run time:
 - Username
 - Password
 - [Unique Device ID](https://android-developers.googleblog.com/2011/03/identifying-app-installations.html)
- The above scheme is hard to crack since:
 - Key is generated at runtime only and not stored anywhere on the device
 - Username and password are stored in account manager and cannot be accessed even with root access
 - Keystore uses the Signing key of the app to generate the encryption key. Even if the all the above information is known, even then it will be hard to generate the same exact encryption key
- Obfuscate your code using progaurd
