# Foundation

## Learn more

- http://developer.apple.com/documentation/foundation.

## Create unique IDs

```
UUID
```

For example:

```swift
import Foundation

let id = UUID()
```

## Create URLs

```
URL
```

For example:

```swift
if let url = URL(string: "https://edge.ldscdn.org/mobile/interview/directory") {
    // Use url
}
```

## Make HTTP requests to a URL

```
URLSession
```

For example:

```swift
import Foundation

func someRequest() async throws {
    guard let url = URL(string: "https://someurl") else {
        // ...
    }
    
    let (data, _) = try await URLSession.shared.data(from: url)
    
    // Use data
}
```

## Decode JSON

```
JSONDecoder
```

For example:

```swift
import Foundation

struct SomeService {
    enum ServiceError: Error {
        case brokenURL
        case missingData
    }
    
    struct SomeResults: Codable {
        // ...
    }
    
    func someRequest() async throws {
        guard let url = URL(string: "https://someurl") else {
            throw ServiceError.brokenURL
        }
        
        let (data, _) = try await URLSession.shared.data(from: url)
        
        if data.isEmpty {
            throw ServiceError.missingData
        }
        
        let someResults = try JSONDecoder().decode(SomeResults.self, from: data)
    
        // Use someResults
    }
}
```
