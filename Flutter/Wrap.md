[![hackmd-github-sync-badge](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg/badge)](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg)
###### Tags: `Flutter` `Dart` `Layout`
# Wrap

### Wrap作用 —— 將溢出螢幕部分自動折行

[Document](https://api.flutter.dev/flutter/widgets/Wrap-class.html)

[Video](https://www.youtube.com/watch?v=z5iw2SeFx2M&list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG&index=4)

<img height="600" src="https://i.imgur.com/L0W65zN.png">


```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_wrap extends StatelessWidget {
  const use_wrap({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Text("未使用Wrap"),
        Row(children: [
          Container(
            color: Colors.amber,
          ),
          Container(),
          Container(
            color: Colors.amber,
          ),
          Container(),
          Container(
            color: Colors.amber,
          ),
          Container(),
          Container(
            color: Colors.amber,
          ),
          Container(),
          Text("=================================================="),
        ]),
        Text("使用Wrap"),
        Wrap(
            spacing: 8.0,//主軸（水平）方向間距
            runAlignment: WrapAlignment.center,//縱軸方向的對齊方式//沿主軸方向之中
            runSpacing: 4.0,//縱軸（垂直）方向的間距
            children: [
              Container(
                color: Colors.amber,
              ),
              Container(),
              Container(
                color: Colors.amber,
              ),
              Container(),
              Container(
                color: Colors.amber,
              ),
              Container(),
              Container(
                color: Colors.amber,
              ),
              Container(),
              Text("=================================================="),
            ]),
        Text("使用direction: Axis.vertical, 設定為直立式"),
      ],
    );
  }
}
```