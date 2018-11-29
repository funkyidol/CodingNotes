# Dialog Fragments
 - Width of `DialogFragment` doesnt really stretch to fit the screen of the UI is primarily made from LinearLayout using layout weigthts. Probably because of this same reason `ConstraintLayout` also doesnt work. To deal with this we have to keep `RelativeLayout` as the root of the UI
