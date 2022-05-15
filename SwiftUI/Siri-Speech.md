###### tags: `Audio` `SwiftUI` `Siri`
# Siri-Speech

I’m going to make my app to talk whatever I wat it to say.  To do that, we need `AVSpeechSynthesizer`

You can check out my article [AVSpeechSynthesizer](https://hackmd.io/@rizzyD/avspeechsynthesizer) to know more about it.

```swift
import SwiftUI
//Remember to import this framework
import AVFoundation

struct ContentView: View {
    
    @State private var text: String = ""
    
    var body: some View {
        
        VStack{
            
            Text(text)
                .padding()
                .font(.title)
                .foregroundColor(Color.red)

            TextField("Type here...", text: $text)          
                .padding()
                
            Button("Speak") {
                
                //create a new AVSpeechSynthesizer
                let synthesizer = AVSpeechSynthesizer()
                //I want to make all the sound stop before I make it speak anything
                synthesizer.stopSpeaking(at: .immediate)

                //setup utterance and make the speech content as the data typed in TextField
                let utterance = AVSpeechUtterance(string: text)
                //speech language
                utterance.voice = AVSpeechSynthesisVoice(language: "en-US")
                //tone
                utterance.pitchMultiplier = 1
                //speech speed
                utterance.rate = 0.4
                //play 
                synthesizer.speak(utterance)
                
            }
            .buttonStyle(.borderedProminent)
            .buttonBorderShape(.capsule)
        }
        
    }
    
}

struct ContentView_Previews: PreviewProvider {
    
    static var previews: some View {
        
        ContentView()
        
    }
    
}
```

# Reference
- [https://medium.com/彼得潘的-swift-ios-app-開發教室/讓-app-開口說話-利用-avspeechsynthesizer-講話-381c5a9e4d40](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E6%95%99%E5%AE%A4/%E8%AE%93-app-%E9%96%8B%E5%8F%A3%E8%AA%AA%E8%A9%B1-%E5%88%A9%E7%94%A8-avspeechsynthesizer-%E8%AC%9B%E8%A9%B1-381c5a9e4d40)
