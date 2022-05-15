###### tags: `SwiftUI` `Picture` `life cycle`

# How to display gif in SwiftUI?

In SwiftUI, gif is not sopported in Image View, if you try `Image(”your_gif_name”)`, it’ll only show a blank page. There are many ways to do it, like using `CGAnimateImageDataWithBloc`, separate your gif into series of image and use `animatedImage` to play those pictures and so on, but I found out that you can also use `WKWebView` (in WebKit) to accomplish it. So let’s get started. 👍  

## Create a new SwiftUI View and add your gif file into folders
![](https://i.imgur.com/EOspfIy.png)

![](https://i.imgur.com/SuWfIID.png)

## Create a new WKWebView

When you use `UIViewRepresentable` , make sure you create `makeUIView` and `updateUIVew` as well.

```swift
//Remember to import WebKit
import WebKit

struct GifImage: UIViewRepresentable {
	func makeUIView(context: Context) -> some WKWebView {
            //make a new webview
	    let webView = WKWebView()
			return webView
	}
	//send data from SwiftUI to UIView
	func updateUIView(_ uiView: UIViewType, context: Context) {
		
	}
}
```

## Setup URL

We need to setup an URL to read our content.

```swift
//bundle is similar to folders
//Bundle.main.url gives access to the resources inside the of the file of the application
let url = Bundle.main.url(forResource: name, withExtension: "gif")!
```

URL needs to be not optional. Use force wrapping(!) to cope with it, it's good to use force here is because we are sure that the gif will be in our app.

:::info
💡 When you use force, make sure that your are sure your data will be in your app, if not then don't use force
:::

In this case we want to read delete.gif, so the resource will be "delete". However, we want to use any kind of gif, so we need to initialize a name.

```swift
//initialize a name
init(_ name: String){
    self.name = name
}
```

## Get URL data

Now we need to extrct infomation from the url, so we will need to create a ++data object++.

```swift
let data = try! Data(contentsOf: url)
```

## Load webView

Load resource into webview; 

```swift
webView.load(
    data, //provide data object
    mimeType: "image/gif", //mimetype is a label to identify a type of data
    characterEncodingName: "UTF-8",
		//deletingLastPath -> delete the last part
    baseURL: url.deletingLastPathComponent()
)
```

## GifImage code

```swift
import SwiftUI
import WebKit

struct GifImage: UIViewRepresentable {
    private let name: String
    
//initialize a name
    init(_ name: String){
        self.name = name
    }
   
    func makeUIView(context: Context) -> some WKWebView {
        let webView = WKWebView()
        
        let url = Bundle.main.url(forResource: name, withExtension: "gif")!
       
        let data = try! Data(contentsOf: url)
       
        webView.load(
            data,
            mimeType: "image/gif",
            characterEncodingName: "UTF-8",
            baseURL: url.deletingLastPathComponent()
        )
 
        webView.scrollView.isScrollEnabled = false
        
        return webView
    }
    
    func updateUIView(_ uiView: UIViewType, context: Context) {
        uiView.reload()
    }
}

struct GifImage_Previews: PreviewProvider {
    static var previews: some View {
        GifImage("delete")
    }
}
```

## ContentView code

```swift
import SwiftUI

struct ContentView: View {
    
    var body: some View {
        VStack{
            List(0 ..< 6){ item in
                GifImage("delete")
                    .frame(width: 200, height: 120, alignment: .center)
                
            }
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```
