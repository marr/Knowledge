# Foundation

## Learn more

- http://developer.apple.com/documentation/foundation

## Create unique IDs

```
UUID
```

For example:

```swift
let someID = UUID()
```

## Create URLs

```
URL
```

For example:

```swift
guard let someURL = URL(string: "https://someurl")
else {
    // ...
}
```

## Make HTTP requests

```
URLSession
```

For example:

```swift
let (someData, someResponse) = try await URLSession.shared.data(from: someURL)
```

## Decode JSON

```
JSONDecoder
```

For example:

```swift
struct SomeOutput: Codable {
    let someKey: Int
    let anotherKey: String
}

let someJSON = """
{
    "someKey": 42,
    "anotherKey": "Hello world"
}
"""

guard let someData = someJSON.data(using: .utf8)
else {
    // ...
}

let someOutput = try JSONDecoder().decode(SomeOutput.self, from: someData)
```

## Use a JSON service

```
URLSession + JSONDecoder
```

For example:

```swift
struct SomeOutput: Codable {
    let someKey: Int
    let anotherKey: String
}

enum SomeError: Error {
    case brokenURL
    case unsuccessfulResponse
    case missingData
}

func someRequest() async {
    do {
        guard let someURL = URL(string: "https://someurl") 
        else {
            throw SomeError.brokenURL
        }
        
        let (someData, someResponse) = try await URLSession.shared.data(from: someURL)
        
        guard (someResponse as? HTTPURLResponse)?.statusCode == 200
        else { 
            throw SomeError.unsuccessfulResponse
        }
        
        if someData.isEmpty {
            throw SomeError.missingData
        }
        
        let someOutput = try JSONDecoder().decode(SomeOutput.self, from: someData)
    
        // ...
    } catch {
        // ...
    }
}
```

## Use notification center

```
NotificationCenter
```

For example:

```swift
NotificationCenter.default.post(name: someValue, object: nil)
```

## Use date formatter

```
DateFormatter
```

For example:

```swift
let dateFormatter = DateFormatter()
dateFormatter.dateFormat = "YYYY-MM-dd"
dateFormatter.timeZone = TimeZone(abbreviation: "UTC")

// String to date
dateFormatter.date(from: "2000-01-01")

// Date to string
dateFormatter.string(from: Date())
```
