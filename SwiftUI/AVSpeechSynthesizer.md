###### tags: `Audio` `SwiftUI` `Siri`
# AVSpeechSynthesizer


In `AVFoundation`, there is a class named`AVSpeechSynthesizer`. With `AVSpeechSynthesizer` you can customize the texts that you want your app to speak.

## <font color="red">`AVSpeechSynthesizer` </font> Declaration

```swift
class AVSpeechSynthesizer : NSObject
```

To configure the way your app speak, like voice, language, contents and so on, we use `AVSpeechUtterance`.

## <font color="red">`AVSpeechUtterance` </font> Declaration

```swift
class AVSpeechUtterance : NSObject
```

## Controlling Speech

```swift
func speak(_ utterance: AVSpeechUtterance)

func continueSpeaking() -> Bool

func pauseSpeaking(at boundary: AVSpeechBoundary) -> Bool

func stopSpeaking(at boundary: AVSpeechBoundary) -> Bool
```

You can notice that above the code we have a enum called `AVSpeechBoundary`. `AVSpeechBoundary` help us specifies when to pauce or stop speech. It contains two constants `immediate` and `word`

- immediate ⇒ Indicates to pause or stop speech immediately.
- word ⇒ Indicates to pause or stop speech after the synthesizer finishes speaking the current word.

## <font color="red">`AVSpeechBoundary`</font> Declaration

```swift
enum AVSpeechBoundary : Int, @unchecked Sendable
```

# Reference

- [AVFoundation](https://developer.apple.com/documentation/avfoundation/)
- [AVSpeechSynthesizer](https://developer.apple.com/documentation/avfaudio/avspeechsynthesizer#declaration)
- [AVSpeechUtterance](https://developer.apple.com/documentation/avfaudio/avspeechutterance)
