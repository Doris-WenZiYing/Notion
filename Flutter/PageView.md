[![hackmd-github-sync-badge](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg/badge)](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg)
###### Tags: `Flutter` `Dart` `Page`
# PageView

## PageView —— 頁面管理

[Document](https://api.flutter.dev/flutter/widgets/PageView-class.html)

[Video](https://www.youtube.com/watch?v=J1gE9xvph-A&list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG&index=10)

```dart
PageView({
    Key? key,
    Axis scrollDirection,//設定 Scroll 是要左右滑動或是上下滑動
    bool reverse,//設定是否要 Scroll 的方向是否反過來
    PageController? controller,
    ScrollPhysics? physics,
    bool pageSnapping,//設定滑動時是否自動下一頁，如果設定 false，在滑動時會卡住前後一頁
    ValueChanged<int>? onPageChanged,
    List<Widget> children = const <Widget>[],
    DragStartBehavior dragStartBehavior,
    bool allowImplicitScrolling,
    String? restorationId,
    Clip clipBehavior,
    ScrollBehavior? scrollBehavior}
)
```

```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_page_view extends StatelessWidget {
  const use_page_view({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
		//設定初始頁數
    final PageController controller = PageController(initialPage: 0);
    return PageView(
      scrollDirection: Axis.horizontal,
      controller: controller,
      children: [
        Center(
          child: Text(
            "Welcome to my space.",
            style: TextStyle(fontSize: 30),
          ),
        ),
        Center(
          child: Text(
            "I'm Doris.",
            style: TextStyle(fontSize: 30),
          ),
        ),
        Center(
          child: Text(
            "Nice to meet you.",
            style: TextStyle(fontSize: 30),
          ),
        ),
      ],
    );
  }
}
```

<img width="200" height="450" align="center" src="https://i.imgur.com/m6IHGaj.gif">
---

## PageController

```dart
PageController({
    int initialPage,//設定第一個要顯示的 Page
    bool keepPage,//當 scrollable 被重建時回復到現在的 Page
    double viewportFraction}
)
```