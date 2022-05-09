###### Tags: `Flutter` `Dart`
# Row & Column 
水平 & 垂直 佈局
![](https://i.imgur.com/STl26ns.png)


```dart
SafeArea(
  child: Row(
    children: <Widget>[Text('A'), Text('B'), Text('C')],
  ),
);
```

```dart
SafeArea(
  child: Column(
    children: <Widget>[Text('A'), Text('B'), Text('C')],
  ),
);
```

| ![](https://i.imgur.com/3vdTEda.jpg)| ![](https://i.imgur.com/fJUA4jw.jpg)|
| -------- | -------- |
| Row    | Column   |

 

# Row

### mainAxisAlignment


(為水平，起始位置在左邊，排列由左至右)

MainAxisAlignment.start:靠左對其

MainAxisAlignment.end: 靠右對齊

MainAxisAlignment.center: 置中

MainAxisAlignment.spaceBetween: 中間留空間

MainAxisAlignment.spaceAround: 兩邊空間均分

MainAxisAlignment.spaceEvenly: 均分空間

### crossAxisAlignment


(為垂直，起始位置在中間，排列由上至下)

CrossAxisAlignment.start: 縱向起點

CrossAxisAlignment.end: 縱向終點

CrossAxisAlignment.center: 縱向中心點

CrossAxisAlignment.stretch: 佔滿縱向

CrossAxisAlignment.baseline: 縱向對齊 baseline

---

>💡 Column 的話就和 Row 相反

# Column

### mainAxisAlignment


(為水平，起始位置在左邊，排列由左至右)

MainAxisAlignment.start:縱向起點

MainAxisAlignment.end: 縱向終點

MainAxisAlignment.center: 縱向中心點

MainAxisAlignment.spaceBetween: 中間留空間

MainAxisAlignment.spaceAround: 兩邊空間均分

MainAxisAlignment.spaceEvenly: 均分空間

### crossAxisAlignment

(為垂直，起始位置在中間，排列由上至下)

CrossAxisAlignment.start: 靠左對齊

CrossAxisAlignment.end: 靠右對齊

CrossAxisAlignment.center: 置中

CrossAxisAlignment.stretch: 佔滿橫向

CrossAxisAlignment.baseline: 橫向對齊 baseline

```dart
Column(
//測試改下面兩行
    mainAxisAlignment: MainAxisAlignment.center,//主軸
    crossAxisAlignment: CrossAxisAlignment.center,//副軸
    children: <Widget>[
      Container(
        color: Colors.redAccent,
        child: Text("A", style: TextStyle(fontSize: 80)),
      ),
      Container(
        color: Colors.blueAccent,
        child: Text("B", style: TextStyle(fontSize: 80)),
      ),
      Container(
        color: Colors.greenAccent,
        child: Text("C", style: TextStyle(fontSize: 80)),
      )
    ],
  ),
```
| <img src="https://i.imgur.com/ljEq9cJ.png">  |<img src="https://i.imgur.com/wmLmWcX.png"> | <img src="https://i.imgur.com/bWkJSPX.png"> | <img src="https://i.imgur.com/krlSy5d.png"> |
| -------- | -------- | --- | -------- |
| Row - 主軸副軸同時在center    | Cloumn - 主軸副軸同時在center     | Cloumn - 主軸副軸同時在start     |Row - 主軸副軸同時在start

