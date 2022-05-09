[![hackmd-github-sync-badge](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg/badge)](https://hackmd.io/epCtheh6Qg6WbSESx9_3Wg)
###### Tags: `Flutter` `Dart` `Layout`
# Table

## Table — 制定表格

[Document](https://api.flutter.dev/flutter/widgets/Table-class.html) 

[Video](https://www.youtube.com/watch?v=_lbE0wsVZSw&list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG&index=11)

<img height="600" src="https://i.imgur.com/2PallDi.png">

```dart
import 'package:flutter/material.dart';

// ignore: camel_case_types
class use_table extends StatelessWidget {
  const use_table({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Table(
        columnWidths: const <int, TableColumnWidth>{
	//制定索引和固定列寬
          0: FixedColumnWidth(200.0),
          1: FixedColumnWidth(50.0),
          2: FixedColumnWidth(180.0),
        },
	//邊框的設定
        border: TableBorder.all(
            color: Colors.black, width: 2.0, style: BorderStyle.solid),
        children: [
          TableRow(children: <Widget>[
	  //TableCell控制Table內容的排列方式
            TableCell(
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceAround,
                children: <Widget>[
                  Text('ID'),
                  Text('NAME'),
                ],
              ),
            )
          ]),
          TableRow(children: <Widget>[
            TableCell(
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceAround,
                children: <Widget>[
                  Text('1'),
                  Text('Doris'),
                ],
              ),
            )
          ]),
          TableRow(children: <Widget>[
            TableCell(
              child: Row(
                mainAxisAlignment: MainAxisAlignment.spaceAround,
                children: <Widget>[
                  Text('2'),
                  Text('Marie'),
                ],
              ),
            )
          ]),
        ],
      ),
    );
  }
}
```