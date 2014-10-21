LDrawer
=======

[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-LDrawer-brightgreen.svg?style=flat)](https://android-arsenal.com/details/1/1042)

Android drawer icon with material design animation

Note
--------
Basically same as appcompat_v7 version 21, you can use appcompat_v7
```groovy
compile 'com.android.support:appcompat-v7:21.0.+'
```
```xml
<style name="AppTheme" parent="Theme.AppCompat.Light">
    <item name="actionBarStyle">@style/ActionBar</item>
</style>

<style name="ActionBar" parent="Theme.AppCompat.Light.DarkActionBar">
    <item name="drawerArrowStyle">@style/AppTheme.DrawerArrowToggle</item>
</style>

<style name="AppTheme.DrawerArrowToggle" parent="Base.Widget.AppCompat.DrawerArrowToggle">
    <item name="color">@android:color/white</item>
</style>
```



Download
--------

via Maven:
```xml
<dependency>
  <groupId>com.ikimuhendis</groupId>
  <artifactId>ldrawer</artifactId>
  <version>0.1</version>
</dependency>
```
or Gradle:
```groovy
compile 'com.ikimuhendis:ldrawer:0.1'
```

![alt tag](https://raw.githubusercontent.com/IkiMuhendis/LDrawer/master/images/animated.gif)

##Usage

You can use like using [normal drawer][2], instead of using `android.support.v4.app.ActionBarDrawerToggle` use `com.ikimuhendis.ldrawer.ActionBarDrawerToggle`

First create `drawerArrow`

```java
drawerArrow = new DrawerArrowDrawable(this) {
        @Override
        public boolean isLayoutRtl() {
            return false;
        }
    };
```
Then create `ActionBarDrawerToggle`

```java
mDrawerToggle = new ActionBarDrawerToggle(this, mDrawerLayout,
        drawerArrow, R.string.drawer_open,
        R.string.drawer_close) {

        public void onDrawerClosed(View view) {
            super.onDrawerClosed(view);
            invalidateOptionsMenu();
        }

        public void onDrawerOpened(View drawerView) {
            super.onDrawerOpened(drawerView);
            invalidateOptionsMenu();
        }
    };
```
You can stop or start animation
```java
mDrawerToggle.setAnimateEnabled(false);
```
You can set `drawerArrow` progress or change color
```java
drawerArrow.setProgress(0f); // normal position
drawerArrow.setProgress(1f); // back arrow position
drawerArrow.setColor(R.color.ldrawer_color); // to set color
```
##Example Projects

  [LDrawer][3]
  [![Google Play](http://developer.android.com/images/brand/en_generic_rgb_wo_45.png)](https://play.google.com/store/apps/details?id=com.ikimuhendis.ldrawer.sample)
  
  [Yemek Tarifleri][4]
  [![Google Play](http://developer.android.com/images/brand/en_generic_rgb_wo_45.png)](https://play.google.com/store/apps/details?id=com.ikimuhendis.android.foodjob)
  

License
=======

    Copyright 2014 İkimühendis

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
    
    
[1]: https://github.com/IkiMuhendis/LDrawer
[2]: http://developer.android.com/training/implementing-navigation/nav-drawer.html
[3]: https://play.google.com/store/apps/details?id=com.ikimuhendis.ldrawer.sample
[4]: https://play.google.com/store/apps/details?id=com.ikimuhendis.android.foodjob
