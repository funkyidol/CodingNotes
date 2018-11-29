### TextInputLayout

There are two ways of Dynamic styling a TextInput layout
1. Create the view component from code 
```java 
TextInputLayout tilTitle = new TextInputLayout(new ContextThemeWrapper(getContext(), R
                .style.TextInputLayoutUsed));
        tilTitle.setLayoutParams(new LinearLayout.LayoutParams(ViewGroup.LayoutParams
                                                                       .MATCH_PARENT, ViewGroup
                                                                       .LayoutParams.WRAP_CONTENT));

        TextInputEditText etTitle = new TextInputEditText(getContext());
        etTitle.setLayoutParams(new LinearLayout.LayoutParams(ViewGroup.LayoutParams
                                                                      .MATCH_PARENT, ViewGroup
                                                                      .LayoutParams.WRAP_CONTENT));
        etTitle.setHint("Name your Offer");
        tilTitle.addView(etTitle);
        llParent.addView(tilTitle);

        TextInputLayout tilDesc = new TextInputLayout(new ContextThemeWrapper(getContext(), R
                .style.TextInputLayoutEarned));
        tilDesc.setLayoutParams(new LinearLayout.LayoutParams(ViewGroup.LayoutParams
                                                                       .MATCH_PARENT, ViewGroup
                                                                       .LayoutParams.WRAP_CONTENT));

        TextInputEditText etDesc = new TextInputEditText(new ContextThemeWrapper(getContext(), R
                .style.TextInputLayoutEarned));
        etDesc.setLayoutParams(new LinearLayout.LayoutParams(ViewGroup.LayoutParams
                                                                      .MATCH_PARENT, ViewGroup
                                                                      .LayoutParams.WRAP_CONTENT));
        etDesc.setHint("Name your Offer");
        tilDesc.addView(etDesc);
        llParent.addView(tilDesc);
```
    
2. Create two separate layout files with different themes applied at xml level and inflate layouts as per the need

 - Style can be defined like so 
```xml
    <style name="TextInputLayoutUsed" parent="ThemeOverlay.AppCompat.Light">
        <!-- Hint color and label color in FALSE state -->
        <item name="android:textColorHint">@color\colorPrimaryUsed<\item>
        <!-- Label color in TRUE state and bar color FALSE and TRUE State -->
        <item name="colorAccent">@color\colorPrimaryUsed<\item>
        <item name="colorControlNormal">@color\colorPrimaryUsed<\item>
        <item name="colorControlActivated">@color\colorPrimaryUsed<\item>
    <\style>
```
and can be applied like so
```xml
<android.support.design.widget.TextInputLayout
        android:id="@+id\til_info"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginEnd="24dp"
        android:layout_marginStart="24dp"
        android:layout_marginTop="16dp"
        app:counterEnabled="true"
        app:counterMaxLength="300"
        android:theme="@style\TextInputLayoutEarned"

        app:hintTextAppearance="@style\create_edittext_hint_appearance">

        <android.support.design.widget.TextInputEditText
            android:id="@+id\et_info"
            style="@style\create_screen_edittext"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Additional Info"
            android:minLines="5"
            android:gravity="start"
            android:inputType="textMultiLine" \>
    <\android.support.design.widget.TextInputLayout>
```
