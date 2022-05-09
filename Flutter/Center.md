[![hackmd-github-sync-badge](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg/badge)](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg)
###### Tags: `Flutter` `Dart`
# Center

****Center 作用 - 使元件置中對齊****

```dart
const Center({
    Key? key,
    double? widthFactor,//將其寬度設置為child的寬度乘以此值。不能為負值！
    double? heightFactor,//將其高度設置為child的高度乘以此值。不能為負值！
    Widget? child}
)
```

```dart
Center(
  child: Container(
    color: Colors.blueGrey,
    child: Text(
      "Hello",
      style: TextStyle(fontSize: 60),
    ),
  ),
);
```
<img width="200" height="450" align="center" src="https://i.imgur.com/MantYCm.png">



