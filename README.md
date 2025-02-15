# Flutter Cupertino Date Picker

[[pub packages]](https://pub.dartlang.org/packages/flutter_cupertino_date_picker)
| [中文说明](./README_zh-cn.md)

Flutter cupertino date picker.

![Example][1]

## Usage

#### 1\. Depend

Add this to you package's `pubspec.yaml` file:

```yaml
dependencies:
  flutter_cupertino_date_picker: ^1.0.5
```

#### 2\. Install

Run command:

```bash
$ flutter packages get
```

#### 3\. Import

Import in Dart code:

```dart
import 'package:flutter_cupertino_date_picker/flutter_cupertino_date_picker.dart';
```

#### 4\. Display DatePicker

##### Bottom Sheet DatePicker

```dart
/// Display date picker in bottom sheet.
///
/// context: [BuildContext]
/// minDateTime: [DateTime] minimum date time
/// maxDateTime: [DateTime] maximum date time
/// initialDateTime: [DateTime] initial date time for selected
/// dateFormat: [String] date format pattern
/// locale: [DateTimePickerLocale] internationalization
/// pickerMode: [DateTimePickerMode] display mode: date(DatePicker)、time(TimePicker)、datetime(DateTimePicker)
/// pickerTheme: [DateTimePickerTheme] the theme of date time picker
/// onCancel: [DateVoidCallback] pressed title cancel widget event
/// onChange: [DateValueCallback] selected date time changed event
/// onConfirm: [DateValueCallback] pressed title confirm widget event
DatePicker.showDatePicker(
  BuildContext context,
  DateTime minDateTime,
  DateTime maxDateTime,
  DateTime initialDateTime,
  String dateFormat,
  DateTimePickerLocale locale: DATETIME_PICKER_LOCALE_DEFAULT,
  DateTimePickerMode pickerMode: DateTimePickerMode.date,
  DateTimePickerTheme pickerTheme: DatePickerTheme.Default,
  DateVoidCallback onCancel,
  DateValueCallback onChange,
  DateValueCallback onConfirm,
});
```

##### DatePicker Widget

```dart
/// Display date picker widget.
///
/// minDateTime: [DateTime] minimum date time
/// maxDateTime: [DateTime] maximum date time
/// initialDateTime: [DateTime] initial date time for selected
/// dateFormat: [String] date format pattern
/// locale: [DateTimePickerLocale] internationalization
/// pickerTheme: [DateTimePickerTheme] the theme of date time picker
/// onCancel: [DateVoidCallback] pressed title cancel widget event
/// onChange: [DateValueCallback] selected date time changed event
/// onConfirm: [DateValueCallback] pressed title confirm widget event
DatePickerWidget({
  DateTime minDateTime,
  DateTime maxDateTime,
  DateTime initialDateTime,
  String dateFormat: DATETIME_PICKER_DATE_FORMAT,
  DateTimePickerLocale locale: DATETIME_PICKER_LOCALE_DEFAULT,
  DateTimePickerTheme pickerTheme: DatePickerTheme.Default,
  DateVoidCallback onCancel,
  DateValueCallback onChange,
  DateValueCallback onConfirm,
})
```

##### TimePicker Widget

```dart
/// Display time picker widget.
///
/// minDateTime: [DateTime] minimum date time
/// maxDateTime: [DateTime] maximum date time
/// initialDateTime: [DateTime] initial date time for selected
/// dateFormat: [String] date format pattern
/// locale: [DateTimePickerLocale] internationalization
/// pickerTheme: [DateTimePickerTheme] the theme of date time picker
/// onCancel: [DateVoidCallback] pressed title cancel widget event
/// onChange: [DateValueCallback] selected date time changed event
/// onConfirm: [DateValueCallback] pressed title confirm widget event
TimePickerWidget({
  DateTime minDateTime,
  DateTime maxDateTime,
  DateTime initialDateTime,
  String dateFormat: DATETIME_PICKER_DATE_FORMAT,
  DateTimePickerLocale locale: DATETIME_PICKER_LOCALE_DEFAULT,
  DateTimePickerTheme pickerTheme: DatePickerTheme.Default,
  DateVoidCallback onCancel,
  DateValueCallback onChange,
  DateValueCallback onConfirm,
})
```

##### DateTimePicker Widget

```dart
/// Display date time picker widget.
///
/// minDateTime: [DateTime] minimum date time
/// maxDateTime: [DateTime] maximum date time
/// initialDateTime: [DateTime] initial date time for selected
/// dateFormat: [String] date format pattern
/// locale: [DateTimePickerLocale] internationalization
/// pickerTheme: [DateTimePickerTheme] the theme of date time picker
/// onCancel: [DateVoidCallback] pressed title cancel widget event
/// onChange: [DateValueCallback] selected date time changed event
/// onConfirm: [DateValueCallback] pressed title confirm widget event
DateTimePickerWidget({
  DateTime minDateTime,
  DateTime maxDateTime,
  DateTime initialDateTime,
  String dateFormat: DATETIME_PICKER_DATE_FORMAT,
  DateTimePickerLocale locale: DATETIME_PICKER_LOCALE_DEFAULT,
  DateTimePickerTheme pickerTheme: DatePickerTheme.Default,
  DateVoidCallback onCancel,
  DateValueCallback onChange,
  DateValueCallback onConfirm,
})
```

#### 5\. DateTimePickerLocale

Support:

- en_us: English (EN) United States ***[Default locale]***
- zh_cn: Chinese (ZH) Simplified
- pt_br: Portuguese (PT) Brazil
- es: Spanish (ES)
- ro: Romanian (RO)
- bn: Bengali (BN)
- ar: Arabic (ar)
- jp: Japanese (JP)
- ru: Russian (RU)

##### Add more language

Fork this project, add language text in `lib/date_picker_i18n.dart` file.

```dart
/// Done widget's text
const Map<DateTimePickerLocale, String> DONE = { ... };

/// Cancel widget's text
const Map<DateTimePickerLocale, String> CANCEL = { ... };

/// en_US
const List<String> EN_US_MONTHS = [ ... ];

/// en_US weeks with full name
const List<String> EN_US_WEEKS_FULL = [ ... ];

/// en_US weeks with short name
const List<String> EN_US_WEEKS_SHORT = [ ... ];
```

#### 6\. dateFormat

|Pattern|Meaning                |e.g.      |
|:----|:------------------------|:---------|
|yyyy |year                     |2019, 2020|
|yy   |year, 2 digits           |19, 20|
|MMMM |month                    |January(en_us), 01(zh_cn)|
|MMM  |month, abbreviated       |Jan(en_us), 01(zh_cn)|
|MM   |month, 2 digits          |01、11
|M    |month                    |1, 11|
|dd   |day in month, 2 digits   |05, 25|
|d    |day in month             |5, 25|
|EEEE |day of week              |Monday(en_us), 星期一(zh_cn)|
|EEE  |day of week, abbreviated |Mon(en_us), 周一(zh_cn)|
|HH   |hour (0~23), 2 digits    |04, 12, 20|
|H    |hour (0~23)              |4, 12, 20|
|mm   |minute, 2 digits         |05, 40|
|m    |minute                   |5, 40|
|ss   |second, 2 digits         |06, 55|
|s    |second                   |6, 55|
|yyyy年|format                   |2019年, 2020年|
|H时   |format                   |5时, 21时|

##### Date Format Separator

Support separator: `|,-._: `.

#### 7\. DateTimePickerTheme

```dart
/// DateTimePicker theme.
///
/// [backgroundColor] DatePicker's background color.
/// [cancelTextStyle] Default cancel widget's [TextStyle].
/// [confirmTextStyle] Default confirm widget's [TextStyle].
/// [cancel] Custom cancel widget.
/// [confirm] Custom confirm widget.
/// [title] Custom title widget. If specify a title widget, the cancel and confirm widgets will not display. Must set [titleHeight] value for custom title widget.
/// [showTitle] Whether display title widget or not. If set false, the default cancel and confirm widgets will not display, but the custom title widget will display if had specified one custom title widget.
/// [pickerHeight] The value of DatePicker's height.
/// [titleHeight] The value of DatePicker's title height.
/// [itemHeight] The value of DatePicker's column height.
/// [itemTextStyle] The value of DatePicker's column [TextStyle].
const DateTimePickerTheme({
  this.backgroundColor: DATETIME_PICKER_BACKGROUND_COLOR,
  this.cancelTextStyle,
  this.confirmTextStyle,
  this.cancel,
  this.confirm,
  this.title,
  this.showTitle: DATETIME_PICKER_SHOW_TITLE_DEFAULT,
  this.pickerHeight: DATETIME_PICKER_HEIGHT,
  this.titleHeight: DATETIME_PICKER_TITLE_HEIGHT,
  this.itemHeight: DATETIME_PICKER_ITEM_HEIGHT,
  this.itemTextStyle: DATETIME_PICKER_ITEM_TEXT_STYLE,
});
```

## Example

[Example sources](https://github.com/wuzhendev/flutter-cupertino-date-picker/tree/master/example)

[Example APK](https://raw.githubusercontent.com/wuzhendev/assets/master/flutter-datepicker/flutter_cupertino_date_picker_v1.0.0.apk)

![Example APK Download](https://github.com/wuzhendev/assets/blob/master/flutter-datepicker/date_picker_qrcode_v1.0.0.png?raw=true)

### DatePicker

![Example: DatePicker][1]

![Example: DatePickerWidget][2]

### TimePicker

![Example: TimePicker][3]

![Example: TimePickerWidget][4]

### DateTimePicker

![Example: DateTimePicker][5]

![Example: DateTimePickerWidget][6]

## License

```
Copyright 2018 wuzhen

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

[1]:https://github.com/wuzhendev/assets/blob/master/flutter-datepicker/flutter_date_picker_14.jpg?raw=true
[2]:https://github.com/wuzhendev/assets/blob/master/flutter-datepicker/flutter_date_picker_15.jpg?raw=true
[3]:https://github.com/wuzhendev/assets/blob/master/flutter-datepicker/flutter_date_picker_16.jpg?raw=true
[4]:https://github.com/wuzhendev/assets/blob/master/flutter-datepicker/flutter_date_picker_17.jpg?raw=true
[5]:https://github.com/wuzhendev/assets/blob/master/flutter-datepicker/flutter_date_picker_18.jpg?raw=true
[6]:https://github.com/wuzhendev/assets/blob/master/flutter-datepicker/flutter_date_picker_19.jpg?raw=true
