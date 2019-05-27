ToolbarBadgeMenuItem
====================

[![Release](https://jitpack.io/v/AchmadHafid/toolbar-badge-menu-item.svg)](https://jitpack.io/#AchmadHafid/toolbar-badge-menu-item)
[![API](https://img.shields.io/badge/API-21%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=21)

Add badge to your toolbar menu item

![image](https://github.com/AchmadHafid/toolbar-badge-menu-item/blob/master/art/demo.gif)



Compatibility
-------------

This library is compatible from API 21 (Android 5.0 Lollipop) & AndroidX.



Download
--------

Add jitpack repository into your root build.gradle

```groovy
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
    ...
  }
}
```

Add the dependency

```groovy
dependencies {
  ...
  implementation 'com.github.AchmadHafid:toolbar-badge-menu-item:2.1'
  ...
}
```



Usage
-----

1. Set it as your toolbar menu item action layout

``` xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">
    
    ...

    <item
        ...
        app:actionLayout="@layout/toolbar_badge_menu_item"
        app:showAsAction="always" />
        
    ...

</menu>
```

2. Override **```onPrepareOptionsMenu```** to build badge

``` kotlin
override fun onPrepareOptionsMenu(menu: Menu?): Boolean {
  createToolbarBadge(
            menu,
            // create a map of itemId & Icon resources
            mapOf(
                R.id.action_show_notification to R.drawable.ic_notifications_none_white_24dp
            ),
            // default background color, use material components theme attribute
            R.attr.colorOnPrimary,
            // default text color, use material components theme attribute
            R.attr.colorPrimary,
            // you can add icon tint color if you want
            R.attr.colorOnPrimary,
            ::getBadgeCount
        )

  return true
}

private fun getBadgeCount(@IdRes id: Int): Int = 
  TODO("do some logic to decide how many badge to show")

```



License
-------

    Copyright 2019 Achmad Hafid

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
       http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
