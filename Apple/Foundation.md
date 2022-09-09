# Foundation

## Use UUID

```
UUID
```

For example:

```swift
let someID = UUID()
```

## Use URL

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

## Use URL session

```
URLSession
```

For example:

```swift
let (someData, someResponse) = try await URLSession.shared.data(from: someURL)
```

## Use JSON decoder

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
URLSession
JSONDecoder
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

## Use date

```
Date
```

For example:

```swift
// The current date and time
Date()

// Add seconds
someDate.addingTimeInterval(60)
```

## Use date formatter

```
DateFormatter
```

For example:

```swift
// Create
let dateFormatter = DateFormatter()

// Date style
dateFormatter.dateStyle = .medium

// Time style
dateFormatter.timeStyle = .none

// String to date
dateFormatter.date(from: someString)

// Date to string
dateFormatter.string(from: someDate)

// Override local values like for unit tests 
dateFormatter.locale = Locale(identifier: "en_US")
dateFormatter.timeZone = TimeZone(abbreviation: "UTC")
dateFormatter.dateFormat = "YYYY-MM-dd"
```

## Use calendar

```
Calendar
```

For example:

```swift
// The current calendar
Calendar.current

// The current calendar with tracking changes
Calendar.autoupdatingCurrent

// Start of day
Calendar.autoupdatingCurrent.startOfDay(for: someDate)

// Specific time
Calendar.autoupdatingCurrent.date(bySettingHour: 17, minute: 0, second: 0, of: someDate)

// Add time
Calendar.autoupdatingCurrent.date(byAdding: .day, value: 7, to: someDate)
Calendar.autoupdatingCurrent.date(byAdding: .minute, value: 30, to: someDate)

// Override local values like for unit tests 
dateFormatter.locale = Locale(identifier: "en_US")
dateFormatter.timeZone = TimeZone(abbreviation: "UTC")
```

## Use user defaults

```
UserDefaults
```

For example:

```swift
// Save
UserDefaults.standard.set(someValue, forKey: someKey)

// Load
UserDefaults.standard.someType(forKey: someKey)

// Delete
UserDefaults.standard.removeObject(forKey: someKey)
```

