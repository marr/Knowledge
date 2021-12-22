# Swift

## Learn more

- http://developer.apple.com/documentation/swift
- http://developer.apple.com/videos/swift

## Create the entry point

```
// Add code at global scope

// Add main.swift file

@main
```

## Print values

```swift
print(someValue)
```

## Create constants

```swift
let someName = someValue
```

## Create variables

```swift
var someName = someValue
```

## Use access control

```
// Restrict to within the enclosing declaration
private

// Restrict to within the module (the default)
[internal]

// Allow outside the module
public
```

## Annotate types when they can’t be inferred

```
: SomeType[?]
```

- `(SomeType, AnotherType) -> SomeType` for functions.
- `String` for text.
- `Character` for text items.
- `Bool` for binary values.
- `Array` for a collection of ordered values.
- `Set` for a collection of unique values.
- `Dictionary` for a collection of key-value pairs.
- `Int` for numbers without a fractional component.
- `Double` for numbers with a fractional component.
- `(SomeType, AnotherType)` for tuples.
- `Void` for an empty tuple (no return value).
- `?` for a value that might be `nil` (optional).

## Convert values to different types

```
SomeType(someValue)
```

## Declare functions

```
func someFunction([someLabel] someParameter: SomeType [= SomeDefaultValue], [anotherLabel] anotherParameter: AnotherType [= SomeDefaultValue]) [async] [throws] [-> SomeType] {
    // ...
}
```

- `async` if caller needs to `await`.
- `throws` if caller needs to `try`.

## Call functions

```
[try] [await] someFunction(someArgument: someValue, anotherArgument: anotherValue)
```

- `try` if function has `throws`.
- `await` if function has `async`.

## Use closure expressions

```
{ // ... }
```

- `{ (someValue, anotherValue) in // body }`.
- `{ // body }` with `$#` for arguments.

## Create instances of structures or classes

```swift
var someInstance = SomeStructOrClass(someInitializerArgument: someValue, anotherInitializerArgument: anotherValue)
```

## Access instance properties of structures or classes

```swift
someInstance.someProperty = someValue
```

## Access instance methods of structures or classes

```swift
someInstance.someMethod()
```

## Create structures

```
struct SomeStruct {
    // Constants / variables for instance properties
    // Functions for instance methods
}
```

## Create classes

```
[final] class SomeClass {
    // Same as structs except shared by reference with inheritance instead of copied by value
}
```

- `final` for preventing subclasses and overrides.

## Compare values

```
==
!=
>
<
>=
<=
```

## Create enumerations

```swift
enum SomeEnum {
    case someCase
    case anotherCase
}
```

## Use enumerations

```swift
SomeEnum.someCase
```

## Add switch statements

```swift
switch someCondition {
case somePattern:
    // ...
case anotherPattern:
    // ...
default:
    // ...
}
```

- `someValue`.
- `someValue, anotherValue`.
- `.someEnumCase`.
- `let someValue where // matching conditions`.

For example:

```swift
enum SomeEnum {
    case someCase
    case anotherCase
}

let someValue = SomeEnum.someCase

switch someValue {
case .someCase:
    // ...
case .anotherCase:
    // ...
}
```

## Add if/else blocks

```
if [let] someCondition[,]
   [let anotherCondition] {
    // ...
} else if anotherCondition {
    // ...
} else {
    // ...
}
```

- `let` for optional bindings.

## Add guards

```swift
guard someCondition else {
    // ...
}
// Continues when someCondition was met
```

## Add ternary logic

```swift
someCondition ? someValue : anotherValue
```

## Create while loops

```swift
while someCondition {
    // ...
}
```

## Create literal strings

```swift
"Some string"
```

## Interpolate values in strings

```swift
"Some string: \(someValue)"
```

## Create literal multiline strings

```swift
"""
Some
string
"""
```

## Check if strings start/end with substrings

```
someString.hasPrefix/hasSuffix(anotherString)
```

## Use encoded data in strings

```
String(data: someData, encoding: .someEncoding)
```

For example:

```swift
print(String(data: someJSON, encoding: .utf8)!)
```

## Create literal characters

```
: Character = "X"
```

## Create literal booleans

```
true
false
```

## Use logical operators on boolean values

```
!someValue
someValue && someValue
someValue || someValue
```

## Access collection items

```swift
someCollection[someKey]
```

- Index number for arrays.

## Iterate over items in collections

```swift
for someItem in someCollection {
    // ...
}
```

- Elements for arrays or sets.
- `(someKey, someValue)` key-value pairs for dictionaries.
- Characters for strings.

## Transform items in collections

```
someCollection.map({ // ... })
```

## Filter items in collections

```
someCollection.filter({ // ... })
```

## Split items in collections

```swift
someCollection.split(separator: someValue)
```

## Join items in collections

```swift
someCollection.joined(separator: someValue)
```

## Sort items in collections

```swift
someCollection.sort()
```

## Reverse items in collections

```swift
someCollection.reverse()
```

## Check if collections contain an item

```swift
someCollection.contains(someValue)
```

## Check if collections are empty

```swift
someCollection.isEmpty
```

## Count items in collections

```swift
someCollection.count
```

## Get the first item in collections

```swift
someCollection.first
```

## Get the last item in collections

```swift
someCollection.last
```

## Get a random item in collections

```swift
someCollection.randomElement()
```

## Create literal arrays

```swift
[someValue, anotherValue]
```

## Create literal sets

```
: Set = [someValue, anotherValue]
```

## Create literal dictionaries

```swift
[
    "someKey": someValue,
    "anotherKey": anotherValue
]
```

## Create literal integers

```
#
```

## Create literal doubles

```
#.#
```

## Perform arithmetic operations

```
+
-
*
/
%
```

## Create literal tuples

```swift
(someName: someValue, anotherName: anotherValue)
```

## Decompose tuple items

```swift
let (someValue, anotherValue) = someTuple
```

## Access tuple items

```swift
someTuple.someValue
```

## Use optional values

```
// Optional binding
if let someValue = someOptional {
    // Use someValue
    // ...
} [else {
    // Handle missing
    // ...
}]

// Guard
guard let someValue = someOptional else {
    // Handle missing
    // ...
}
// Use someValue
// ...

// Optional chaining operator
someOptional?.someMethod

// Nil-coalescing operator 
someOptional ?? someDefaultValue

// Can fail at runtime so confirm first
if someOptionalValue != nil {
    // Forced unwrap operator
    someOptional!
}
```

## Throw runtime errors

```swift
throw SomeError
```

For example:

```swift
enum VendingMachineError: Error {
    case invalidSelection
    case insufficientFunds(coinsNeeded: Int)
    case outOfStock
}

throw VendingMachineError.insufficientFunds(coinsNeeded: 5)
```

## Handle functions that can throw runtime errors

```swift
func someFunction() throws {
    // Might throw an error
    // ...
}

do {
    try someFunction()
    // No error was thrown
} catch {
    // An error was thrown
}
```

## Create a task

```swift
Task {
    // Some asynchronous code
}
```

## Add comments

```swift
// Some single line comment

/* Some multi line
comment. */
```

## Ignore items

```swift
_
```

For example:

```swift
func someFunction(_ someParameter: SomeType) {
    // ...
}

someFunction(someValue)

for (_, someValue) in someDictionary {
    // ...
}

for _ in 1...10 {
    // ...
}
```

## Create ranges

```
[start]...[end]
```

For example:

```swift
Array(someArray[0...42])

for name in names[42...] {
    //  …
}

for i in 1...10 {
    // ...
}
```

## Add availability conditions

```
#available(someCondition, anotherCondition, *)
```

For example:

```swift
if #available(iOS 10, macOS 10.12, *) {
    // Use iOS 10 APIs on iOS, and use macOS 10.12 APIs on macOS
} else {
    // Fall back to earlier APIs
}
```
