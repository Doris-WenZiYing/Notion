###### Tags: `Flutter` `Dart`
# Text

****<font size=4.5>Text元件常用屬性</font>****


- data：要顯示的文字
- maxLines：文字顯示行數
- style：可以設定字體大小、顏色等樣式
- textDirection：文字顯示方向


## maxLine

```dart
Text(
    "未加入maxLine:\nHello World\n1\n2\n3\n4\n5\n",
    style: TextStyle(fontSize: 30)
)
```
<img width="200" height="450" align="center" src="https://i.imgur.com/RIiFCnk.png">

```dart
Text(
  "加入maxLine:\nHello World\n1\n2\n3\n4\n5\n",
  maxLines: 4,//設定只能顯示4行
  style: TextStyle(fontSize: 30)//設定字體大小
),
```
<img width="200" height="450" align="center" src="https://i.imgur.com/xmUJNGh.png">

## TextStyle

```dart
TextStyle({
    Color? color,
    TextDecoration? decoration,//加底線、刪除線等等
    Color? decorationColor,
    TextDecorationStyle? decorationStyle,
    double? decorationThickness,
    FontWeight? fontWeight,
    FontStyle? fontStyle,
    TextBaseline? textBaseline,
    String? fontFamily,
    List<String>? fontFamilyFallback,
    double? fontSize,
    double? letterSpacing,
    double? wordSpacing,
    double? height,
    TextLeadingDistribution? leadingDistribution,
    Locale? locale,
    Paint? background,
    Paint? foreground,
    List<Shadow>? shadows,
    List<FontFeature>? fontFeatures}
)
```
