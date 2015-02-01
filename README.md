Fabuless
========

Fun to use [Floating Action Button][2] (FAB) view for Android 4.0 and higher.

![fab][1]

Features
=======

 - Fully configurable via layout xml-file
 - Can be attached to any view in layout
 - Automatically caclulatable attachment position
 - Two fab sizes ('normal' and 'small')
 - Nice reveal and touch animations

Usage example
=======

  To attach a `FabView` to your target view, do the following.

  1. Wrap target view with a `FrameLayout`.
  2. Add `com.halfbit.fabview.FabView` as the last child of that `FrameLayout`.
  3. Configure size, location, color and icon of `FabView`.
  
  That's it. Here is an example.

```xml
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:fabview="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <RelativeLayout
      android:id="@+id/fab_target"
	    android:layout_width="match_parent"
	    android:layout_height="170dp"
	    android:layout_gravity="top"
	    android:background="@color/color1">
    
      <!--
        This is yours target view with children (ommited for simplisity) 
        ... 
      -->
    
    </RelativeLayout>
    
    <!-- This is our FabView -->
    <de.halfbit.fabview.FabView 
        android:id="@+id/fab"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:background="@color/fab_color"
        android:paddingTop="3dp"
        android:src="@drawable/ic_favorite"
        fabview:fab_attachTo="@id/fab_target"
        fabview:fab_attachAt="bottom_right"
        fabview:fab_attachType="border"
        fabview:fab_size="normal"
        fabview:fab_padding="16dp"
        fabview:fab_revealAfterMs="300"
        />

</FrameLayout>
```

FabView attributes
=======

| Attribute | Required | Default | Description
| --------- | :------: | ------- | -----------
| `fab_attachTo` | X | - | `Id` of target view.
| `fab_attachAt` | - | `top_right` | Attachment position (`top_left`, `top_right`, `bottom_left`, `bottom_right`).
| `fab_attachType` | - | `border` | Defines whether the button resides inside (`inside`) parent container or it gets attached to parent's borders (`border`).
| `fab_size` | - | `normal` | Fab size (`normal`, `small`).
| `fab_padding` | - | 16dp | Padding to the closest left or right border of target view.
| `fab_revealAfterMs` | - | Show immediately | When set, fab will be revealed with animation after a specified timeout in milliseconds.


Other attributes
=======

`FabView` is an `ImageView`. You can use any `ImageView` attributes to achieve required look and feed. For instance 
  * to set an icon you can use `android:src` attribute
  * to change background color you can use `android:background` attribute
  * to move icon down you can use `android:paddingTop` attribute etc.


More details
=======

  * Click animation only works when `OnClickListener` is set to the view
  * Method `setBackgroundDrawable()` method supports `ColorDrawable` only


License
=======

    Copyright (c) 2014 Sergej Shafarenka, halfbit.de

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


[1]: web/fab.gif
[2]: http://www.google.com/design/spec/patterns/promoted-actions.html#promoted-actions-floating-action-button
