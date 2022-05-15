###### tags: `SwiftUI` `UIView`
# UIViewRepresentable

## Declariation

```swift
//Convert a UIView from UIKit to SwiftUI
protocol UIViewRepresentable : View where Self.Body == Never
```

`UIViewRepresentable` is a simple wrapper that we can use to take UIKit components and put them into SwiftUI.

So what does `UIViewRepresentable` do exactly? It can encapulate UIKit into SwiftUI View, and then we will be able to reuse all the components in UIKit easily.

There are two protocols that must be introduced.

```swift
//creating a UIView that you want to show
func makeUIView(context: Self.Context) -> Self.UIViewType

//send data from SwiftUI to UIKit
func updateUIView(_ uiView: Self.UIViewType, context: Self.Context)
```

Now if you want to send some data to SwiftUI from UIView, for example you make a UITextField, when you type in this fied, the data won’t show it on SwiftUI. In order to make SwiftUI and UIKit View to interact with each other, you need a special method to cope with it. This is where `makeCoordinator`comes in. 

```swift
//send data from UIKit to SwiftUI
func makeCoordinator() -> Self.Coordinator
```

Coordinator can help you forward your delegate from your UIView to any SwiftUI views.

# Reference

- [UIViewRepresentable](https://developer.apple.com/documentation/swiftui/uiviewrepresentable/)
- [Coordinator](https://developer.apple.com/documentation/swiftui/uiviewrepresentable/makecoordinator()-9e4i4)