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

## Import modules

```swift
import SomeModule
```

## Annotate types when they can’t be inferred

```
: [SomeType.]SomeType[?]
```

- `(someParameter: SomeType, anotherParameter: AnotherType) -> SomeType` for functions.
- `SomeStruct` for structures.
- `SomeClass` for classes.
- `SomeEnum` for enumerations.
- `(someName: SomeType, anotherName: AnotherType)` for tuples.
- `Void` for an empty tuple (no return value).
- `String` for text.
- `Character` for text items.
- `Bool` for binary values.
- `Array` for a collection of ordered values.
- `Set` for a collection of unique values.
- `Dictionary` for a collection of key-value pairs.
- `Int` for numbers without a fractional component.
- `Double` for numbers with a fractional component.
- `?` for a value that might be `nil` (optional).

## Convert values to different types

```
SomeType(someValue)
```

## Create functions

```
func someFunction([someLabel] someParameter: SomeType [= SomeDefaultValue], [anotherLabel] anotherParameter: AnotherType [= SomeDefaultValue]) [async] [throws] [-> SomeType] {
    // ...
}
```

- `async` if caller needs to `await`.
- `throws` if caller needs to `try`.

## Use functions

```
[try] [await] someFunction(someArgument: someValue, anotherArgument: anotherValue)
```

- `try` if function has `throws`.
- `await` if function has `async`.

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

## Use a do-catch statement

```swift
do {
    try someFunction()
    // No error was thrown
} catch {
    // An error was thrown
    // Can use "error"
}
```

## Use optional chaining operators

```
?
```

For example:

``` 
someOptional?.someMethod
try? someFunction()
```

## Use nil-coalescing operators

```
??
```

For example:

```swift
someOptional ?? someDefaultValue
```

## Use closures

```
{ // ... }
```

- `{ someValue, anotherValue in // body }`.
- `{ // body }` with `$#` for argument values.

## Use trailing closures

```
someFunction { // ... }
```

## Use structures or classes

```swift
let someStructOrClass = SomeStructOrClass(someArgument: someValue, anotherArgument: anotherValue)
```

## Use properties of structures or classes

```swift
someStructOrClass.someProperty = someValue
```

## Use methods of structures or classes

```swift
someStructOrClass.someMethod()
```

## Create structures

```
struct SomeStruct {
    // Functions for methods
    // Constants / variables for stored properties
    // Variables with { // ... } for computed properties
    // Variables with { didSet { // ... } } for property observers
    // @SomePropertyWrapper for property wrappers
    // self for the instance itself - used by default when using a property / method name within a method like [self.]someProperty
    // init() to customize initialization
}
```

For example:

```swift
struct SomeStruct {
    func someFunction() -> SomeType {
        // ...
    }
    
    let someName: SomeType = someValue
    
    var someName: SomeType {
        // ...
    }
    
    @SomePropertyWrapper var someName: SomeType
    
    private let someParameter: SomeType 
    
    init(someParameter: SomeType) {
        self.someParameter = someParameter
    }
}
```

## Create classes

```
[final] class SomeClass {
    // Same as structs except reference instead of value
}
```

- `final` for preventing subclasses and overrides.

## Create enumerations

```swift
enum SomeEnum {
    case someCase
    case anotherCase
}
```

## Use enumerations

```swift
[SomeEnum].someCase
[SomeEnum].someCase.rawValue
[SomeEnum].allCases
```

## Add switch conditions

```swift
switch someValue {
case [let] someCondition[,] [let anotherCondition]:
    // ...
[case anotherCondition:
    // ...]
[default:
    // ...]
}
```

- `let` for optional binding.

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

## Add guard conditions

```swift 
guard [let] someCondition[,]
      [let anotherCondition]
else {
    // ...
}
```

- `let` for optional binding.

## Add if/else conditions

```
if [let] someCondition[,]
   [let anotherCondition] {
    // ...
} [else if anotherCondition {
    // ...
}] [else {
    // ...
}]
```

- `let` for optional binding.

## Add ternary conditions

```swift
someCondition ? someValue : anotherValue
```

## Create while loop conditions

```swift
while someCondition {
    // ...
}
```

## Compare values

```
==
!=
>
<
>=
<=
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

## Uppercase strings

```swift
someString.uppercased
```

## Lowercase strings

```swift
someString.lowercased
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

## Check if collections are empty

```swift
someCollection.isEmpty
```

## Count items in collections

```swift
someCollection.count
```

## Iterate over items in collections

```swift
for someItem in someCollection {
    // ...
}
```

## Get a random item in collections

```swift
someCollection.randomElement()
```

## Create arrays from collections 

```swift
Array(someCollection)
```

## Create literal arrays

```swift
[someValue, anotherValue]
```

## Merge arrays

```
someArray + anotherArray 
```

For example:

```swift
someArray + [someValue]
```

## Map items in arrays

```
someArray.map { // ... }
```

## Compact map items in arrays

```
someArray.compactMap { // ... }
```

## Filter items in arrays

```
someArray.filter { // ... }
```

## Reduce items in arrays

```
someArray.reduce(initial, { result, item in // ... }
```

## Find the first match in arrays

```
someArray.first(where: { // ... })
```

## Split items in arrays

```swift
someArray.split(separator: someValue)
```

## Join items in arrays

```swift
someArray.joined(separator: someValue)
```

## Sort items in arrays

```swift
someArray.sort()
```

## Reverse items in arrays

```swift
someArray.reversed()
```

## Check if arrays contain an item

```swift
someArray.contains(someValue)
someArray.contains(where: { // ... })
```

## Get the first item in arrays

```swift
someArray.first
```

## Get the last item in arrays

```swift
someArray.last
```

## Get a prefix of items in arrays

```swift
someArray.prefix(someValue)
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

For example:

```swift
let someDictionary = [
    "someKey": someValue,
    "anotherKey": anotherValue
]

let anotherDictionary = [:]
```

## Decompose values from dictionary items

```
(someKey, someValue)
```

## Use dictionary keys

```swift
someDictionary.keys
```

## Merge dictionaries

```
someDictionary.merging(anotherDictionary) { // ... }
```

- Can use common options like `uniquingKeysWith`.

For example:

```swift
let someDictionary = [
    "someKey": 10,
    "anotherKey": 20
]

let anotherDictionary = [
    "someKey": 5
]

let mergedDictionary = someDictionary.merging(anotherDictionary, uniquingKeysWith: +)
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

## Access tuple values

```swift
someTuple.someValue
```

## Decompose tuple values

```
(someValue, anotherValue)
```

## Create protocols

```swift
protocol SomeProtocol {
    // Property requirements
    // Method requirements
    // Initializer requirements
}
```

For example:

```swift
protocol SomeProtocol {
    var someProperty: SomeType { get }
    var anotherProperty: AnotherType { get }
}

// Can provide default implementations
extension SomeProtocol {
    var someProperty: SomeType {
        // ...
    }
    
    var anotherProperty: AnotherType {
        // ...
    }
}
```

## Use protocols

```
SomeType: SomeProtocol, AnotherProtocol
// Provide implementations
```

For example:

```swift
struct SomeStruct: Identifiable {
    let id = UUID()
}

enum SomeEnum: CaseIterable {
    case someCase
    case anotherCase
}
```

## Create a task

```swift
// Some synchronous top-level
Task {
    // Some asynchronous code
}
```

## Use async-let

```swift
async let someOutput = someFunction()

await someOutput
```

```swift
async let someOutput = someFunction()
async let anotherOutput = anotherFunction()

let allOutput = await [someOutput, anotherOutput]
```

## Use withTaskGroup

```
await withTaskGroup(of: SomeType.self) { taskGroup in
    taskGroup.addTask {
        // ...
    }
}
```

For example:

```swift
await withTaskGroup(of: SomeType.self) { taskGroup in
    for someItem in someCollection {
        taskGroup.addTask { await someFunction(someItem) }
    }
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
    // ...
}

for i in 1...10 {
    // ...
}
```

## Check availability

```
#available(someAvailability, anotherAvailability, *)
```

For example:

```swift
if #available(iOS 10, macOS 10.12, *) {
    // ...
} else {
    // ...
}
```

## Mark availability

```
@available(someAvailability, anotherAvailability, *)
```

- Can be versions / `renamed` / `deprecated`.

For example:

```swift
@available(iOS 10, macOS 10.12, *)
func someFunction() {
    // ...
}

func someFunction() {
    // ...
}

@available(*, renamed: "anotherFunction()")
func anotherFunction(completion: @escaping (Result<SomeType, Error>) -> Void) {
    // ...
}

func anotherFunction() async throws -> SomeType {
    return try await withCheckedThrowingContinuation { continuation in
        anotherFunction() { result in
            continuation.resume(with: result)
        }
    }
}
```
