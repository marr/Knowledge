# Core Data

## Learn more

- https://developer.apple.com/documentation/coredata

## Add persistence

```
NSPersistentContainer
```

For example:

```swift
import CoreData

struct Persistence {
    static let shared = Persistence()

    static var preview: Persistence = {
        let result = Persistence(inMemory: true)
        let viewContext = result.container.viewContext
        
        let someEntity = SomeEntity(context: viewContext)
        someEntity.someProperty = someValue
        
        do {
            try viewContext.save()
        } catch {
            let nsError = error as NSError
            fatalError("Unresolved error \(nsError), \(nsError.userInfo)")
        }
        
        return result
    }()

    let container: NSPersistentContainer

    init(inMemory: Bool = false) {
        container = NSPersistentContainer(name: "SomeName")
        if inMemory {
            container.persistentStoreDescriptions.first!.url = URL(fileURLWithPath: "/dev/null")
        }
        container.loadPersistentStores(completionHandler: { (storeDescription, error) in
            if let error = error as NSError? {
                fatalError("Unresolved error \(error), \(error.userInfo)")
            }
        })
    }
}
```

## Connect an app to persistence

```
.environment(\.managedObjectContext, viewContext)
```

For example:

```swift
import SwiftUI

@main
struct SomeApp: App {
    let persistence = Persistence.shared
    
    var body: some Scene {
        WindowGroup {
            ContentView()
                .environment(\.managedObjectContext, persistence.container.viewContext)
        }
    }
}
```

## Connect a view to persistence

```
@Environment
@FetchRequest
```

For example:

```swift
import SwiftUI
import CoreData

struct ContentView: View {
    @Environment(\.managedObjectContext) private var viewContext

    @FetchRequest(
        sortDescriptors: [NSSortDescriptor(keyPath: \SomeEntity.someProperty, ascending: true)],
        animation: .default)
    private var someEntities: FetchedResults<SomeEntity>
    
    var body: some View {
        // Use someEntities
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
            .environment(\.managedObjectContext, Persistence.preview.container.viewContext)
    }
}
```

## Update persistence

```
viewContext.save()
```

For example:
   
```swift
let someEntity = SomeEntity(context: viewContext)
someEntity.someProperty = someValue
    
do {
    try viewContext.save()
} catch {
    // ...
}
```
