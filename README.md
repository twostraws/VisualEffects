<h1 align="center">Visual Effects</h1>

<p align="center">
    <img src="https://img.shields.io/badge/iOS-13.0+-blue.svg" />
    <img src="https://img.shields.io/badge/macOS-10.15+-brightgreen.svg" />
    <img src="https://img.shields.io/badge/Swift-5.3-orange.svg" />
    <a href="https://twitter.com/twostraws">
        <img src="https://img.shields.io/badge/Contact-@twostraws-lightgrey.svg?style=flat" alt="Twitter: @twostraws" />
    </a>
</p>

**If you're able to target iOS 15 and later, this repository is no longer needed because there is dedicated SwiftUI API for this now.** See here: [How to add visual effect blurs](https://www.hackingwithswift.com/quick-start/swiftui/how-to-add-visual-effect-blurs)

<hr />

This repository is a wrapper for `UIVisualEffectView` and `NSVisualEffectView`, which will be useful until SwiftUI introduces an official view that does the same.

SwiftUI does not have an official `UIVisualEffectView` wrapper, so a number of folks have attempted to make one with varying degrees of success. Fortunately for all of us, Apple has released their own wrapper for both iOS and macOS, licensed under the MIT license. This repository hosts that wrapper as a Swift package, so you can use it yourself.

I ([Paul Hudson](https://twitter.com/twostraws)) have made only tiny changes to their code to aid readability, and to allow it to work across both platforms from a single package.


## Example code

This will place a `VisualEffectBlur` over a linear gradient, with some text inside the blur getting a vibrancy effect.

```swift
import SwiftUI
import VisualEffects

struct ContentView: View {
    var body: some View {
        ZStack {
            LinearGradient(
                gradient: Gradient(colors: [.red, .blue]),
                startPoint: .topLeading,
                endPoint: .bottomTrailing
            )

            VisualEffectBlur(blurStyle: .systemUltraThinMaterial, vibrancyStyle: .fill) {
                Text("Hello World!")
                    .font(.largeTitle)
            }
        }
    }
}
```



## License

This package is released under the MIT license, as shown below.

Copyright © 2020 Apple Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
