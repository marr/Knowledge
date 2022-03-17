# Combine

## Learn more

- https://developer.apple.com/documentation/combine

## Use publishers

```
NotificationCenter.default.publisher(for: someValue)
    .someOperators
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
