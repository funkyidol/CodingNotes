# Android Notes

### Tips for using EventBus
1. When dealing with Android lifecycle with eventbus, make sure subscribers are registered at the earliest possible stage and any calls follow after.

### Broadcast Receivers
**Implementation steps**

1. Create a class to implement `BroadcastReceiver` and write the logic for handling the broadcast.
2. Register the receiver in `AndroidManifest.xml` and specify the permission it must have in order to listen to the said broadcast.
       <receiver android:name="MyPhoneReceiver" >
            <intent-filter>
                <action android:name="android.intent.action.PHONE_STATE" >
                </action>
            </intent-filter>
       </receiver>
3. Give the app the necessary permissions to enable receiving the said broadcast.

**Tip**
* In order to send local broadcasts, create an intent that points to the required broadcast.
