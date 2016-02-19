AvatarView
==============
A circular ImageView or TextView with colorful background for showing avatar.

This is based on [CircleImageView from hdodenhof](https://github.com/hdodenhof/CircleImageView) and [FitTextView from SUKOHI](https://github.com/SUKOHI/FitTextView)

![AvatarView](https://raw.github.com/teejoe/AvatarView/master/demo.png)

Features
==============

* Display circular image / text.
* Text auto fitting in circle.
* Display colorful background for different text.
* Customize background color generator.

Gradle integration
==================

Minimum code for Gradle integration, place code in your `build.gradle`

```
dependencies {
    compile 'com.m2x:AvatarView:1.0.1'
}
```

Usage
============

* Add code in your layout.xml:

    ```
    <com.m2x.avatarview.AvatarView
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:layout_margin="10dp"
        android:padding="5dp"
        app:avtv_fit_text_length="5"
        app:avtv_random_fill_color="true"
        app:avtv_text="text1"
        app:avtv_text_size="40sp"/>
    ```

* Customize backgounrd color generator

    You can override computeFillColor() to make you own background color generator. Currently its based on the text content:
    
    ```
    protected int computeFillColor() {
        if (mText == null) {
            return mFillColor;
        }

        int length = ((mText.length() > 10) ? 10 : mText.length());

        int value = 0;
        for (int i = 0; i < length; i++) {
            value += mText.charAt(i);
        }
        value *= 12345;

        int red = 100 + ((value & 0x00ff0000) >> 17);
        int green = 100 + ((value & 0x0000ff00) >> 9);
        int blue = 100 + ((value & 0x000000ff) >> 1);

        return Color.argb(255, red, green, blue);
    }
    ```

License
============

    Copyright 2014-2015 M2X

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
