# Combine

## Learn more

- https://developer.apple.com/documentation/combine

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
