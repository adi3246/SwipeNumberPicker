# SwipeNumberPicker

The library provides simple number picker. The number is selected with the swipe gesture, to right - increase, to left - decrease value. Also, by click NumberPickerDialog will be shown.

  ![Demo](snp.gif)


[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-SwipeNumberPicker-green.svg?style=true)](https://android-arsenal.com/details/1/3025)

# Usage

Just add the dependency to your `build.gradle`:

```groovy
dependencies {
    compile 'com.github.supervital:swipenumberpicker:1.0.3'
}
```

In layout:

```xml
<com.vi.swipenumberpicker.SwipeNumberPicker
	android:id="@+id/number_picker"
	android:layout_width="wrap_content"
	android:layout_height="wrap_content"
	android:layout_alignParentBottom="true"
	android:layout_alignParentLeft="true"
	app:snp_numberColor="@android:color/white"
	app:snp_arrowColor="@android:color/white"
	app:snp_backgroundColor="@color/colorAccent"
	app:snp_max="1000"
	app:snp_min="50"
	app:snp_value="95"/>
```

Attributes:

``` xml
	<attr name="snp_min" format="integer"/>
	<attr name="snp_max" format="integer"/>
	<attr name="snp_value" format="integer"/>
	<attr name="snp_arrowColor" format="color"/>
	<attr name="snp_backgroundColor" format="color"/>
	<attr name="snp_numberColor" format="color"/>
```

To set changed value implement the `OnValueChangeListener` listener and on `onValueChange` return `true`

```Java
	swipeNumberPicker.setOnValueChangeListener(new OnValueChangeListener() {
		@Override
		public boolean onValueChange(SwipeNumberPicker view, int oldValue, int newValue) {
			boolean isValueOk = (newValue & 1) == 0;
			if (isValueOk)
				result1.setText(Integer.toString(newValue));
	
			return isValueOk;
		}
	});
```

Also you can:
* disable/enable SwipeNumberPicker;
* disable/enable Showing of a NumberPicker Dialog. If the dialog disabled `View.OnClickListener` will be called;
* set the dialog title;
* set min, max values;
* set value;
* set intermediate mode.


# Change Log

###### v1.0.1
	Initial release
###### v1.0.2
	Prefixed custom attributes to avoid any issue
###### v1.0.3
	Implemented intermediate mode suggested [MFlisar](https://github.com/MFlisar)
	
	
# License

    Copyright (C) 2015 Vitalii Ishchuk

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

         http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
