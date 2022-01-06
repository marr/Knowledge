# Xcode

## Learn more

- http://developer.apple.com/documentation/xcode
- http://developer.apple.com/videos/developer-tools

## View developer documentation

```
Window > Developer Documentation
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

## Navigate project files/groups

```
Project Navigator
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
```

## Find in project

```
Find > Find in Project
Find Navigator
Find/Replace
Scope
```

## Find in file

```
Find > Find
Find/Replace
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

## Clean build folder

```
Product > Clean Build Folder
```

## Reset package caches

```
File > Packages > Reset Package Caches
```

## Clear app data in Simulator

```
Home Screen > Long Press App Icon > Delete > Re-build
```

## Clean all data in Simulator

```
Device > Erase All Content and Settings
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

## Rename

```
Right Click > Refactor > Rename
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
Action Menu > Add Documentation
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
Debug Area > View Hierarchy Button
Orient to 3D
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
