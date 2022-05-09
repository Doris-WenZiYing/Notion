[![hackmd-github-sync-badge](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg/badge)](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg)
###### Tags: `Flutter` `Dart`
# Flutter Intro
<font size=8> 一開始給的程式碼：</font>

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title:
          'Flutter Widget of the Week Demo', //這裡的title 在 Android 上，標題顯示在任務管理器的應用快照上方，當用戶按下“最近使用的應用”按鈕時會顯示這些快照 在 Web 上，它用作頁面標題，顯示在瀏覽器的打開選項卡列表中，ios無效果。
      theme: ThemeData(
        primarySwatch: Colors.blue, //控制主要風格的顏色可以更改為他顏色試試看 ex Colors.green
      ),
      home: MyHomePage(title: 'Widget of the Week'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  MyHomePage({Key? key, required this.title}) : super(key: key);

  // This widget is the home page of your application. It is stateful, meaning
  // that it has a State object (defined below) that contains fields that affect
  // how it looks.

  // This class is the configuration for the state. It holds the values (in this
  // case the title) provided by the parent (in this case the App widget) and
  // used by the build method of the State. Fields in a Widget subclass are
  // always marked "final".

  final String title;

  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      // This call to setState tells the Flutter framework that something has
      // changed in this State, which causes it to rerun the build method below
      // so that the display can reflect the updated values. If we changed
      // _counter without calling setState(), then the build method would not be
      // called again, and so nothing would appear to happen.
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    // This method is rerun every time setState is called, for instance as done
    // by the _incrementCounter method above.
    //
    // The Flutter framework has been optimized to make rerunning build methods
    // fast, so that you can just rebuild anything that needs updating rather
    // than having to individually change instances of widgets.
    return Scaffold(
      appBar: AppBar(
        // Here we take the value from the MyHomePage object that was created by
        // the App.build method, and use it to set our appbar title.
        title: Text(widget.title), //最上面的bar
      ),
      body: Center(
        // Center is a layout widget. It takes a single child and positions it
        // in the middle of the parent.
        child: Text("將這個text替換成想看的widget"), //改成想展示的元件
      ),
    );
  }
}
```

## 分檔案的main

```dart
import 'package:flutter/material.dart';
// ignore: unused_import
import 'SafeArea/safe_area.dart';//這裡加入要使用的檔案路徑

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
        home: Scaffold(
            appBar: AppBar(title: Text('MyApp')), body: use_safe_area()));//這裡宣告檔案名字
  }
}
```

## StatelessWidget & StatefulWidget

Flutter 狀態分成兩種，無狀態(StatelessWidget)和有狀態(StatefulWidget)

- 無狀態(StatelessWidget)：
    
    初始化後都不會改變狀態的widget，就選擇無狀態
    
- 有狀態(StatefulWidget)：
    
    StatelessWidget是靜態的，在初始化後，並不會重建自己。反之StatefulWidget可以透過setState再次重繪
    
## 狀態選擇方式

- 大部分使用StatelessWidget，當需要setState方式更新狀態時，才需要使用StatefulWidget狀態
- StatefulWidget 運算成本比較昂貴，勿濫用，若需使用盡量安排使用在末子節點上，且讓元件數量降至最少，減少降低系統重繪的成本



>💡 透過<font color="red">`stless`</font> 或 <font color="red">`stful`</font> 關鍵字，快速生成程式碼，節省時間。



