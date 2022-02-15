# Xcode

## Learn more

- http://developer.apple.com/documentation/xcode
- http://developer.apple.com/videos/developer-tools

## View developer documentation

```
Window > Developer Documentation
{Type} > Click
```

## Build/run

```
Play Icon
```

- Opens simulator by default.

## Switch the active scheme

```
{Platform} > {Device}
```

## View reports

```
Report Navigator
```

## View errors/warnings

```
Issue Navigator
Breadcrumbs > Error/Warning Icon
```

## Navigate project files/groups

```
Project Navigator
Breadcrumbs
```

## Navigate symbols inside a file

```
Breadcrumbs > Symbols
```

## Pin files

```
File > Double Click
```

## View action menu

```
Symbol > Command + Click
```

## View quick help

```
Symbol > Option + Click
```

## Move forward/backward

```
Back/Forward Arrows
```

## Auto complete

```
{type}<tab>[<tab>]
```

## Show debug area

```
View > Debug Area > Show Debug Area
```

## Use breakpoints

```
Line # > Toggle
Run
Debug Area
Breakpoint Navigator
Column > Command + Click > Set Column Breakpoint
```

## Add integrated todo comments

```
// TODO: Some thing
```

## Add integrated marks

```
// MARK: Some thing
// MARK:- Some thing
```

## Address inline errors/warnings

```
Click > [Fix]
```

## Find in project

```
Find > Find in Project
Find Navigator
Find/Replace
Search Scopes
```

## Find in file

```
Find > Find
Find/Replace
```

## Use matching braces

```
Brace > Double Click
```

## Find selected items

```
Select > Find > Find Selected Symbol in Workspace
Select > Find > Find Selected Text in Workspace
```

## Navigate selected items

```
Select > Navigate > Reveal In Project Navigator
```

## Re-indent selected lines

```
Select > Editor > Structure > Re-Indent
```

## Clean build folder

```
Product > Clean Build Folder > Restart Xcode
```

## Reset package caches

```
File > Packages > Reset Package Caches
```

## Delete derived data

```
Preferences > Locations > Open Derived Data Path In Finder > Close Xcode > Delete Derived Data Content > Restart Xcode > File > Packages > Resolve Package Versions
```

## Delete device app data

```
Simulator > Home Screen > Long Press App Icon > Delete
```

## Erase device data/settings

```
Simulator > Device > Erase All Content and Settings
```

## Create projects

```
File > New > Project
```

- Multiplatform App.
- Package.
- Empty.

## Create playgrounds

```
File > New > Playground
```

## Create project packages

```
File > New > Package
```

## Create files

```
{Select Parent Group}
File > New > File
```

- Source.
- View.
- Data Model.
- Markdown.

## Create groups

```
{Select Parent Group}
File > New > Group
```

## Change file targets

```
File Inspector > Target Membership
```

## Add existing files

```
File > Add Files to {Project}
```

## Open quickly

```
File > Open Quickly
```

## Refactor

```
Right Click > Refactor
```

## Rename

```
Right Click > Refactor > Rename > [Toggle] > Rename
```

## Upgrade syntax

```
Edit > Convert > Syntax
```

## View project documentation

```
Product > Build Documentation
```

## Add project documentation

```
Editor > Structure > Add Documentation
```

## Run tests

```
Line # > Play Icon
Test Navigator
```

## Create a unit test target

```
Tests Navigator > Plus Icon > New Unit Test Target
```

## Create unit tests

```swift
import XCTest
@testable import SomeModule

final class SomeThingTests: XCTestCase {
    func testSomeBehavior() {
        // Assertions
    }

    func testAnotherBehavior() {
        // Assertions
    }

    // ...
}
```

- `XCTAssertEqual(someValue, anotherValue)` for input/output comparisons.
- `XCTUnwrap(someOptional)` for optionals.

For example:

```swift
import XCTest
@testable import SomeModule

final class FormatBirthdateTests: XCTestCase {
    func testConvertsValidBirthdates() {
        XCTAssertEqual(formatBirthdate(date: "1900-01-23"), "01/23/1900")
    }

    func testHasEmptyStringForInvalidFormatting() {
        XCTAssertEqual(formatBirthdate(date: "1-2-1903"), "")
    }

    func testHasEmptyStringForInvalidDates() {
        XCTAssertEqual(formatBirthdate(date: "1900-23-23"), "")
    }
}
```

## Use package dependencies

```
{Project Name} > {Project Name} > Package Dependencies
Plus/Minus Icon
Row > Version Number
```

## Temporarily override package dependencies

```
Finder > Drag and drop the source under the project
Make and test changes
Remove the reference
```

## Update package dependencies

```
Right Click > Update Package
```

## Use build settings

```
{Project Name} > {Project Name} > Build Settings
{Target}
```

## Use build phases

```
{Project Name} > {Target} > Build Phases.
```

## Display UI canvas

```
Editor > Canvas
UI Inspector
```

## Add UI controls

```
Toolbar > Plus Icon
Drag & Drop > Canvas / Code
```

## Add UI previews

```
Canvas > Plus Icon
```

## Toggle UI live preview

```
Canvas > Play Icon
```

## Inspect UI view hierarchy

```
Debug Area > Debug View Hierarchy Button
Orient to 3D
Inspectors
```

## Create a UI test target

```
Tests Navigator > Plus Icon > New UI Test Target
```

## Create UI tests

```swift
import XCTest

class SomeThingTests: XCTestCase {
    override func setUpWithError() throws {
        continueAfterFailure = false
        // ...
    }

    override func tearDownWithError() throws {
        // ...
    }

    func testSomeBehavior() throws {
        let app = XCUIApplication()
        app.launch()
        // Assertions
    }
}
```

For example:

```swift
import XCTest

class LaunchTests: XCTestCase {
    override func setUpWithError() throws {
        continueAfterFailure = false
    }
    
    func testRendersProfileBrowseWithData() throws {
        let app = XCUIApplication()
        app.launch()
        XCTAssertTrue(app.staticTexts["Luke Skywalker"].exists)
        XCTAssertTrue(app.staticTexts["Darth Vader"].exists)
    }

    func testRendersProfileDetailWithData() throws {
        let app = XCUIApplication()
        app.launch()
        app.staticTexts["Kylo Ren"].tap()
        XCTAssertTrue(app.staticTexts["Born on 10/31/1987"].exists)
        XCTAssertTrue(app.staticTexts["Force Sensitive"].exists)
    }

    func testLaunchPerformance() throws {
        measure(metrics: [XCTApplicationLaunchMetric()]) {
            XCUIApplication().launch()
        }
    }
}
```

## Record interactions in UI tests

```
Place Cursor Inside Test > Record Icon > {Do Interactions} > Stop Icon
```

## Record UI test performance baselines

```
Run Performance Test > Performance Result Icon > Set Baseline
```
