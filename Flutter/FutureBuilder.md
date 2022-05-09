[![hackmd-github-sync-badge](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg/badge)](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg)
###### Tags: `Flutter` `Dart` `Async`
# FutureBuilder

### FutureBuilder作用 —— 異步UI更新

[Document](https://api.flutter.dev/flutter/widgets/FutureBuilder-class.html)

[video](http://youtube.com/watch?v=ek8ZPdWj4Qo&list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG&index=8)

```dart
FutureBuilder({
  this.future,
  this.initialData,
  @required this.builder,
})
```

- `future`：`FutureBuilderFuture`
- `initialData`：初始數據，用戶設置默認數據。
- `builder`：Widget構建器；該構建器會在`Future`

```dart
AsyncWidgetBuilder = Function (BuildContext context, AsyncSnapshot snapshot)
```

`snapshot`會包含當前異步任務的狀態信息及結果信息，比如我們可以通過`snapshot.connectionState` `snapshot.hasError` `AsyncSnapshot`

```dart
enum ConnectionState {
  // 當前沒有異步任務，比如[FutureBuilder]的[future]為null時
  none,

  // 異步任務為等待狀態
  waiting,

  // Stream處於激活狀態（stream上已经有數據傳遞了），對於FutureBuilder沒有該狀態。
  active,

  // 異步任務終止.
  done,
}
```

```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_future_builder extends StatefulWidget {
  const use_future_builder({Key? key}) : super(key: key);

  @override
  _use_future_builder createState() => _use_future_builder();
}

// ignore: camel_case_types
class _use_future_builder extends State<use_future_builder> {
  Future<String> mockNetworkData() async {
		//模擬取資料的過程，中間隔2秒，返回一個字串
    return Future.delayed(Duration(seconds: 2), () => "Internet data");
  }

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        crossAxisAlignment: CrossAxisAlignment.center,
        children: [
          FutureBuilder(
            future: mockNetworkData(),
            builder: (BuildContext context, AsyncSnapshot<String> snapshot) {
              // ignore: unused_local_variable
              List<Widget> children;
              //請求結束
              if (snapshot.connectionState == ConnectionState.done) {
                if (snapshot.hasError) {
                  //請求失敗，顯示錯誤
                  return Text(
                    "Error: ${snapshot.error}",
                    style: TextStyle(fontSize: 40),
                  );
                } else {
                  //請求成功，顯示數據
                  return Text(
                    "Result: ${snapshot.data}",
                    style: TextStyle(fontSize: 40),
                  );
                }
              } else {
                //請求未結束，顯示loading
                return SizedBox(
                  child: CircularProgressIndicator(),//前面等待中轉圈圈的標誌
                  width: 75,
                  height: 75,
                );
              }
            },
          ),
        ],
      ),
    );
  }
}
```