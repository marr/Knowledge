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

## Use view modifiers

```
SomeView { ... }
.someViewModifier()

SomeView()
    .someViewModifier()
```

For example:

```
SomeView { ... }
.padding()
.background(.green)
.border(.blue)
.opacity(0.5)
.frame(width: 100)
.task {
    // ...
}
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

For example:

```swift
Text("Some text")
    .font(.title)
    .bold()
    .italic()
    .lineLimit(1)
    .foregroundColor(.red)
```

## Add progress views

```swift
ProgressView()
```

## Add image views

```swift
Image(...)
```

- `systemName: "someSFSymbol"` for vector system images.
- `"some-file"` for raster images.

For example:

```swift
Image("SomeImage")
    .resizable()
    .aspectRatio(contentMode: .fit)
    .cornerRadius(5)
```

## Add async image views

```swift
AsyncImage(url: someURL))

AsyncImage(url: someURL)) { image in
    // ...
} placeholder: {
    // Views
}
```

For example:

```swift
AsyncImage(url: URL(string: "https://someurl"))
    .frame(width: 200, height: 200)

AsyncImage(url: URL(string: "https://someurl")) { image in
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
.disabled
.alert("Some alert", isPresented: $someName) {
    Button("Ok", role: .cancel) { }
}
.sheet(isPresented: $someName) {
    // Views
}
```

## Add menu views

```
Menu("Some menu") {
    // Views
}
```

For example: 

```
Menu("Some menu") {
    Button(...)
    Button(...)
}
```

## Add toggle views

```swift
Toggle("Some label", isOn: $someName)
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

## Add z stack views

```swift
ZStack {
    // Views
}
```

For example:

```swift
ZStack {
    Color.purple
        .ignoresSafeArea()
    Text("Some item")
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
.refreshable {
    // Use await for indicator duration
}
.task {
    // Use await for indicator duration
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

## Add section views

```swift
Section(header: // Views) {
    // Views
}
```

For example:

```swift
ForEach(items) { item in
    Section(header: Text(item.title)) {
        // Views
    })
}
```

## Use ObservableObject

```
SomeClass: ObservableObject {
    // @Published on properties to expose external data that can change
}
```

## Use @ObservedObject

```
struct SomeView: View {
    // @ObservedObject on properties to subscribe to published changes of observable objects
    
    var body: some View {
        // Views
    }
}
```

## Use @EnvironmentObject

```
struct SomeView: View {
    // @EnvironmentObject on properties to gain access to observable objects stored in the environment
    
    var body: some View {
        // Views
    }
}
```

## Use @Binding

```
struct SomeView: View {
    // @Binding on properties to share write access without taking ownership - derive with $ like $someProperty
    
    var body: some View {
        // Views
    }
}
```

## Use @State

```
struct SomeView: View {
    // @State on properties to create transient state local to views
    
    var body: some View {
        // Views
    }
}
```

- `private` recommended to keep local.

For example:

```swift
@State private var someName = someValue
```

## Add previews for views

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
