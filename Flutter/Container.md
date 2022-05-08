###### Tags: `Flutter` `Dart`
# Container


### Container作用 —— 容器

[Document](https://api.flutter.dev/flutter/widgets/Container-class.html)

[Video](https://www.youtube.com/watch?v=c1xLMaTUWCY)

```dart
Container({
  this.alignment,//對齊
  this.padding, //外部間距，容器內補白，屬於decoration的裝飾範圍
  Color color, // 背景色
  Decoration decoration, // 背景裝飾
  Decoration foregroundDecoration, //前景裝飾
  double width,//容器的寬度
  double height, //容器的高度
  BoxConstraints constraints, //容器大小的限制條件（最大高/寬度、最小高/寬度） 
  this.margin,//內部間距，容器外補白，不屬於decoration的裝飾
  this.transform, //變換
  this.child,//可設定一個子元件
})
```


 | On the right is a Container     | ![](https://i.imgur.com/Oj7qsIX.png =200x) 
 | --- |:------------------------------------------:|


```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_container extends StatelessWidget {
  const use_container({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisAlignment: MainAxisAlignment.center,//圖形置中
      children: [
        Center(
          child: Container(
            height: 100,//長度
            width: 100,//寬度
            color: Colors.blueGrey,//顏色
          ),
        ),
      ],
    );
  }
}
```

---

### AnimatedContainer作用 —— 使Container有動畫

[Document](https://api.flutter.dev/flutter/widgets/AnimatedContainer-class.html)

[Video](https://www.youtube.com/watch?v=yI-8QHpGIP4&list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG&index=5)

```dart
AnimatedContainer({
            this.alignment,//對齊
            this.padding,//容器內補白
            Color color,//背景色
            Decoration decoration,//背景裝飾
            Decoration foregroundDecoration,//前景裝飾
            double width,//容器的寬度
            double height,//容器的高度
            BoxConstraints constraints,//容器大小的條件限制
            this.margin,//容器外補白
            this.transform,//變換
            this.transformAlignment,
            this.child,
            this.clipBehavior = Clip.none,
            Curve curve = Curves.linear,
            required Duration duration,
            VoidCallback onEnd}
)
```


```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_animated_container extends StatefulWidget {
  const use_animated_container({Key? key}) : super(key: key);

  @override
  _use_animated_containerState createState() => _use_animated_containerState();
}

// ignore: camel_case_types
class _use_animated_containerState extends State<use_animated_container> {
  bool selected = false;
  // ignore: non_constant_identifier_names
  void switch_Container() {
    setState(() {
      selected = !selected;
    });
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector( //手勢
      onTap: () { //點一下
        switch_Container();//進行轉換
      },
      child: Center(
        child: AnimatedContainer(
          width: selected ? 200.0 : 100.0,
          height: selected ? 100.0 : 200.0,
          color: selected ? Colors.blueGrey : Colors.black,
          alignment:
              selected ? Alignment.center : AlignmentDirectional.topCenter,
          duration: const Duration(seconds: 1),
        ),
      ),
    );
  }
}
```

---

## color屬性


- 直接設定顏色

```dart
Container(color: Colors.red)//設定為紅色
```

- 使用8 個 16 進制設定顏色

```dart
Container(color: Color(0xFFFF0000))
```

- 使用 ARGB 設定顏色 (A,R,G,B)，第一個欄位為 Alpha 透明度

```dart
Container(color: Color.fromARGB(255, 255, 00, 00))
```

---

## alignment 屬性


Alignment常數值

Alignment.bottomCenter：置底中間

Alignment.bottomLeft：左下角

Alignment.center：正中間

Alignment.centerLeft：置左邊中間

Alignment.centerRight 置右中間

Alignment.topCenter：正上方中間

Alignment.topLeft：左上角

Alignment.topRight：右上角

---

## constraints 屬性

```dart
Center(
      child: Container(
          padding: EdgeInsets.all(20.0),
          color: Colors.blueGrey,
          alignment: Alignment.center, //文字置中
          child: Text(
            "Hello",
            style: TextStyle(fontSize: 40),
          ),
          constraints: BoxConstraints(
              maxHeight: 300,
              maxWidth: 300,
              minHeight: 50,
              minWidth: 50)))
```

| 透過 constraints 畫出一個正方形   | ![](https://i.imgur.com/mDi04xi.png =200x)
 | --- |:------------------------------------------:|


---

## margin屬性


- margin: EdgeInsets.all()，一個值設定四個邊的間距

```dart
Center(
      child: Container(
      margin: EdgeInsets.all(50.0),
      color: Colors.blueGrey,
      alignment: Alignment.center, //文字置中
      child: Text(
        "Hello",
        style: TextStyle(fontSize: 40),
      ),
    ))
```
![](https://i.imgur.com/VG7Ao2n.png =200x)




- EdgeInsets.only()，分別設定四邊的不一樣間距

```dart
Center(
      child: Container(
        margin: EdgeInsets.only(
	left: 50, top: 10, right: 100, bottom: 10),
        color: Colors.blueGrey,
        alignment: Alignment.center, //文字置中
        child: Text(
          "Hello",
          style: TextStyle(fontSize: 40),
        ),
      ),
    );
```
![](https://i.imgur.com/y5ctGzu.png =200x)



---

## padding 屬性


- EdgeInsets.only()，分別設定四邊的不一樣間距

```dart
Center(
      child: Container(
      color: Colors.blueGrey,
      child: Text(
        'Hello',
        style: TextStyle(fontSize: 30),
      ),
      padding: EdgeInsets.only(left: 50, top: 100, right: 100, bottom: 10),
    ));
```
![](https://i.imgur.com/BdantCF.png =200x)

