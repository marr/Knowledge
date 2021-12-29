# SwiftUI

## Learn more

- http://developer.apple.com/documentation/swiftui
- http://developer.apple.com/videos/swiftui-ui-frameworks

## Create apps

```swift
import SwiftUI

@main
struct SomeApp: App {
    var body: some Scene {
        // Scene
    }
}
```

For example:

```swift
import SwiftUI

@main
struct SomeApp: App {
    var body: some Scene {
        WindowGroup {
            SomeView()
        }
    }
}
```

## Create views

```swift
import SwiftUI

struct SomeView: View {
    var body: some View {
        // Views
    }
}
```

## Use views

```
SomeView { ... }
```

## Add conditional UI inside of views

```
// if / switch
```

## Add a modifier to a view

```
SomeView { ... }
.someModifier()
```

For example:

```
.navigationTitle("Some title)
.padding()
.font(.title)
.foregroundColor(.red)
.aspectRatio(contentMode: .fit)
.cornerRadius(5)
.onAppear {
    // ...
}
```

## Add navigation views

```swift
NavigationView {
    SomeView()
        .navigationTitle("Some title)
}
```

## Add navigation link views

```swift
NavigationLink(destination: SomeView()) {
    // Views
}
```

## Add tab views

```swift
TabView {
    SomeView()
        .tabItem {
            Label("Some label", systemImage: "someSFSymbol")
        }
    AnotherView()
        .tabItem {
            Label("Some label", systemImage: "someSFSymbol")
        }
}
```

## Add text views

```swift
Text("Some text")
```

## Add progress views

```swift
ProgressView()
```

## Add image views

```swift
Image(systemName: "someSFSymbol")
```

## Add async image views

```swift
AsyncImage(url: URL(string: someURL)) { image in
    // ...
} placeholder: {
    // Views
}
```

For example:

```swift
AsyncImage(url: URL(string: someURL)) { image in
    image.resizable()
} placeholder: {
    ProgressView()
}
.aspectRatio(contentMode: .fit)
```

## Add label views

```swift
Label("Some label", systemImage: "someSFSymbol")
```

## Add button views

```swift
Button(action: someAction) {
    // Views
}
```

For example:

```swift
Button(action: someAction) {
    Label("Some label", systemImage: "someSFSymbol")
}

Button(action: someAction) {
    Text("Some text")
}
```

## Add text field views

```swift
TextField("Some label", text: someValue)
```

## Add vertical stack views

```swift
VStack {
    // Views
}
```

For example:

```swift
VStack(alignment: .leading) {
    Label("Gift", systemImage: "gift")
    Label("Bolt", systemImage: "bolt")
}
```

## Add horizontal stack views

```swift
HStack {
    // Views
}
```

## Add list views

```
List[(someCollection)] {
    // Views
}
```

- `someCollection` with closure expression items.

For example:

```swift
List {
    Text("Some item")
    Text("Another item")
}

List(items) { item in
    Text(item.text)
}
```

## Add for each views

```swift
ForEach(someCollection) {
    // Views
}
```

For example:

```swift
ForEach(items) { item in
    Text(item.text)
}
```

## Add spacer views

```swift
Spacer()
```

## Create state variables inside of views

```
@State // Variable
```

For example:

```swift
@State private var someName = someValue
```

## Use state variables inside of views

```
someName
```

For example:

```swift
Image(systemName: isPlaying ? "pause.circle" : "play.circle")
```

## Update state variables inside of views

```swift
someName = someValue

someBoolean.toggle()
```

For example:

```swift
Button(action: {
    isPlaying.toggle()
}) {
    Image(systemName: isPlaying ? "pause.circle" : "play.circle")
}
```

## Bind to state variables inside of views

```
$someName
```

For example:

```swift
TextField("Username", text: $username)
```

## Use binding arguments inside of views

```
@Binding // Variable
```

For example:

```swift
@Binding var someName: SomeType
```

## Add previews

```
SomeView { ... }

struct SomeView_Previews: PreviewProvider {
    static var previews: some View {
        SomeView()
    }
}
```

For example:

```swift
struct SomeView_Previews: PreviewProvider {
    static var previews: some View {
        Group {
            SomeView(someProperty: someValue)
            
            SomeView(someProperty: someValue)
                .environment(\.sizeCategory, .accessibilityExtraExtraExtraLarge)
                .previewDisplayName("Dynamic Type")
        }
    }
}
```
