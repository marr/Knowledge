# Combine

## Use observable objects

```
SomeClass: ObservableObject {
    // @Published on published properties
}
```

## Use publishers

```
somePublisher
    .someOperator(s)
    .someSubscriber
```

For example:

```swift
NotificationCenter.default.publisher(for: someValue)
    .receive(on: DispatchQueue.main)
    .map { // ... }
    .filter { // ... }
    .debounce { // ... }
    .sink { // ... }
```
