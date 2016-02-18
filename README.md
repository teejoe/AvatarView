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

Usage
==============

* Add attrs to res/values/attrs.xml

    ```
    <declare-styleable name="AvatarView">
        <attr name="avtv_border_width" format="dimension" />
        <attr name="avtv_border_color" format="color" />
        <attr name="avtv_border_overlay" format="boolean" />
        <attr name="avtv_fill_color" format="color" />
        <attr name="avtv_random_fill_color" format="boolean" />
        <attr name="avtv_text" format="string" />
        <attr name="avtv_text_color" format="color" />
        <attr name="avtv_text_size" format="dimension" />
        <attr name="avtv_fit_text_length" format="integer" />
    </declare-styleable>
    ```
* Copy com.m2x.avatarview.AvatarView.java(in library project) to your project.
* Add code in your layout.xml:

    ```
    <com.m2x.avatarview.AvatarView
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:layout_margin="10dp"
        android:padding="5dp"
        app:avtv_fill_color="#009900"
        app:avtv_fit_text_length="5"
        app:avtv_random_fill_color="true"
        app:avtv_text="text1"
        app:avtv_text_size="40sp"/>
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
