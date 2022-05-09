[![hackmd-github-sync-badge](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg/badge)](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg)
# SafeArea

### SafeArea 作用 —— 加邊界

[Document](https://api.flutter.dev/flutter/widgets/SafeArea-class.html)

[Video](https://www.youtube.com/watch?v=lkF0TQJO0bA&list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG&index=2)

<div class="row">
  <div class="row">
      使用SafeArea
    <img width="200" height="400" src="https://i.imgur.com/3XQqRDr.png"> 
       未使用SafeArea
       <img width="200" height="400" src="https://i.imgur.com/aGd0ek1.png"> 
    </div>  
</div>




```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_safe_area extends StatelessWidget {
  const use_safe_area({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return SafeArea(
      minimum: EdgeInsets.all(10),//加邊界（數字設定為邊界大小），也可以只設定單邊
			left: true,//上下左右都是bool型態
			right: true,
			top: true,
			bottom: true,
      child: ListView(
        children: List.generate(
          100,
          (index) => Text(
            "index is $index",
            style: TextStyle(fontSize: 20, color: Colors.blueGrey),
          ),
        ),
      ),
    );
  }
}
```