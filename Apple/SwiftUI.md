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
.contextMenu {
    Button("Some text", action: someAction)
}
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
Button("Some text", action: someAction)
```

For example:

```swift
Button("Some text", action: { print("Hello world" })

Button(action: someAction) {
    Label("Some label", systemImage: "someSFSymbol")
}

Button("Some text", action: someAction)
    .disabled

Button("Some text", action: someAction)
    .confirmationDialog(
        someTitle,
        isPresented: $someName
    ) {
        Button("Some text", role: .destructive) {
            // ...
        }
        Button("Some text", role: .cancel) {
            someName = false
        }
    }

Button("Some text", action: someAction)
    .alert("Some alert", isPresented: $someName) {
        Button("Some text", role: .cancel, action: someAction)
    }

Button("Some text", action: someAction)
    .sheet(isPresented: $someName) {
        // Views
    }
```

## Add vertical stack views

```swift
VStack {
    // Views
}
```

- `spacing` to specify the spacing between items.
- `alignment` to specify the alignment of items.

For example:

```swift
VStack(spacing: 0, alignment: .leading) {
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

- `spacing` to specify the spacing between items.
- `alignment` to specify the alignment of items.

For example:

```swift
HStack(spacing: 10, alignment: .top) {
    Text("Some text")
    Text("Some text")
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
    Text("Some text")
}
```

## Add list views

```
List {
    // Views
}
```

- `someCollection` with closure expression items.

For example:

```swift
List {
    Text("Some text")
    Text("Another text")
}

List(items) { item in
    Text(item.text)
}
.refreshable {
    // Use await for indicator duration
}

List {
    ForEach(items) { item in
        Text(item.text)
    }
    .onDelete { // ... }
    .onMove { // ... }
}
.toolbar {
    EditButton()
}

List {
    Text("Some text")
    Text("Another text")
}
.toolbar {
    ToolbarItem(placement: .primaryAction) {
        Button(action: someAction) {
            Label("Some label", systemImage: "someSFSymbol")
        }
    }
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

## Add menu views

```
Menu("Some label") {
    // Views
}
```

For example: 

```
Menu("Some label") {
    Button(...)
    Button(...)
}
```

## Add toggle views

```swift
Toggle("Some label", isOn: $someValue)
```

## Add text field views

```swift
TextField("Some label", text: $someValue)
```

## Add picker views

```
Picker("Some label", selection: $someValue) {
    // Views
}
```

For example: 

```
List {
    Picker("Some label", selection: $someValue) {
        ForEach(SomeEnum.allCases) {
            Text($0.label)
        }
    }
}

Picker("Some label", selection: $someValue) {
    Text("Some text").tag(0)
    Text("Another text").tag(1)
}
.pickerStyle(.segmented)
```

## Use observable objects

```
SomeClass: ObservableObject {
    // @Published on properties to expose external data that can change
}
```

## Use observed objects

```
struct SomeView: View {
    // @ObservedObject on properties to subscribe to published changes of observable objects
    
    var body: some View {
        // Views
    }
}
```

## Use environment objects

```
struct SomeView: View {
    // @EnvironmentObject on properties to gain access to observable objects stored in the environment
    
    var body: some View {
        // Views
    }
}
```

## Use bindings

```
struct SomeView: View {
    // @Binding on properties to share write access without taking ownership - derive with $ like $someProperty
    
    var body: some View {
        // Views
    }
}
```

## Use state

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

## Use view builders

```
struct SomeView: View {
    // @ViewBuilder on properties to create views from closures
    
    var body: some View {
        // Views
    }
}
```

- `private` recommended to keep local.

For example:

```swift
struct SomeView: View {
    var body: some View {
        someSection
        anotherSection
    }
    
    @ViewBuilder private var someSection: some View {
        // Views
    }

    @ViewBuilder private var anotherSection: some View {
        // Views
    }
}
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
