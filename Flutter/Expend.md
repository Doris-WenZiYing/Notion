[![hackmd-github-sync-badge](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg/badge)](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg)
###### Tags: `Flutter` `Dart` `Flex`
# Expanded

### Expanded作用 —— 空間配置

[Document](https://api.flutter.dev/flutter/widgets/Expanded-class.html)

[Video](https://www.youtube.com/watch?v=_rnZaagadyo&list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG&index=3)

```dart
const Expanded({
int flex = 1,
required this.child}
)
```

### 透過flex設定獲得不同比例的空間配置

<img width="200" height="400" src="https://i.imgur.com/5NHobZ3.png">
<text>   </text>
<img width="200" height="400" src="https://i.imgur.com/ZobOd3l.png">

```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_expanded extends StatelessWidget {
  const use_expanded({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Row(
        mainAxisAlignment: MainAxisAlignment.center, //中間對齊
        children: [
          Expanded(
            flex: 1,//設定比例
            child: Container(
              height: 75,
              width: 75,
              color: Colors.red,
            ),
          ),
          Expanded(
            flex: 1,
            child: Container(
              height: 75,
              width: 75,
              color: Colors.blue,
            ),
          ),
          Expanded(
            flex: 1,
            child: Container(
              height: 75,
              width: 75,
              color: Colors.green,
            ),
          ),
        ],
      ),
    );
  }
}
```
