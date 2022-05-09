[![hackmd-github-sync-badge](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg/badge)](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg)
###### Tags: `Flutter` `Dart` `Animated` `Layout`
# Opacity

### Opacity作用 —— 更改不透明度

[Document](https://api.flutter.dev/flutter/widgets/Opacity-class.html)

[Video](https://www.youtube.com/watch?v=9hltevOHQBw&list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG&index=6)

```dart
const Opacity({
    required this.opacity,//透明度
    this.alwaysIncludeSemantics = false,
    this.child}
)
```
<img width="200" height="450" align="center" src="https://i.imgur.com/GfXd5YB.gif">


```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_opacity extends StatefulWidget {
  const use_opacity({Key? key}) : super(key: key);

  @override
  _use_animated_containerState createState() => _use_animated_containerState();
}

// ignore: camel_case_types
class _use_animated_containerState extends State<use_opacity> {
  bool selected = false;
  // ignore: non_constant_identifier_names
  void switch_Container() {
    setState(() {
      selected = !selected;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          Opacity(
            opacity: selected ? 0.0 : 1.0,
            child: Text(
              "Now you see me",
              style: TextStyle(fontSize: 30),
            ),
          ),
          TextButton(onPressed: switch_Container, child: Text("Show")),
          TextButton(onPressed: switch_Container, child: Text("Hide"))
        ],
      ),
    );
  }
}
```

### AnimatedOpacity作用 —— 動畫式的更改透明度

[Document](https://api.flutter.dev/flutter/widgets/AnimatedOpacity-class.html)

[video](https://youtu.be/QZAvjqOqiLY)

```dart
const AnimatedOpacity({
    this.child,
    required this.opacity,
    Curve curve = Curves.linear,
    required Duration duration,
    VoidCallback? onEnd,
    this.alwaysIncludeSemantics = false}
)
```
<img width="200" height="450" align="center" src="https://i.imgur.com/V5qelgW.gif">

```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_animated_opacity extends StatefulWidget {
  const use_animated_opacity({Key? key}) : super(key: key);

  @override
  _use_animated_opacity createState() => _use_animated_opacity();
}

// ignore: camel_case_types
class _use_animated_opacity extends State<use_animated_opacity> {
  double opacityLevel = 1.0;
  bool selected = false;
  // ignore: non_constant_identifier_names
  void switch_Container() {
    setState(() {
      selected = !selected;
      opacityLevel = opacityLevel == 0 ? 1.0 : 0.0;//透明度設定
    });
  }

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          AnimatedOpacity(
              child: Container(
                color: Colors.blueGrey,
                height: 75,
                width: 75,
              ),
              opacity: opacityLevel,
              duration: const Duration(seconds: 2)),//動畫持續的時間
          TextButton(onPressed: switch_Container, child: Text("Fade")),
          TextButton(onPressed: switch_Container, child: Text("Show")),
        ],
      ),
    );
  }
}
```