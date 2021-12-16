# JavaScript

## Learn more

- https://tc39.es/ecma262/

## Create APIs that can be shared across files (modules)

```
export default someThing
export anotherThing
```

## Use APIs that are shared across files (modules)

```
import someThing, { anotherThing } from "some-path";
await import("some-path");
```

## Create functions

```
(someParameter) => ...
```

## Use a default value for function parameters

```
(someParameter = someValue) => ...
```

## Create asynchronous functions that return an unresolved value (promise)

```
async (someParameter) => ...
```

## Use asynchronous functions that return an unresolved value (promise)

```
await someFunction();
```

## Apply a function on every item in an array

```
someArray.map(someItem => // return updated item)
```

## Get items in an array that meet a condition

```
someArray.filter(someItem => // return boolean for the condition)
```

## Check if all items in an array meet a condition

```
someArray.every(someItem => // return boolean for the condition)
```

## Check if at least one item in an array meets a condition

```
someArray.some(someItem => // return boolean for the condition)
```

## Get the first item in an array that meets a condition

```
someArray.find(someItem => // return boolean for the condition)
```

## Convert an array to a single value

```
someArray.reduce((someAccumulation, someItem)  => // return accumulation, someInitialValue)
```

## Get whether an array contains a value

```javascript
someArray.includes(someValue);
```

## Remove falsy values from an array

```javascript
someArray.filter((someItem) => !!someItem);
```

## Sort an array

```javascript
someArray.sort();
```

## Reverse an array

```javascript
[...someArray].reverse();
```

## Get the unique items in an array

```javascript
[...new Set(someArray)];
```

## Get a portion of an array by index

```javascript
someArray.slice(someStartIndex, someEndIndex);
```

## Get the index of an item in an array

```javascript
someString.indexOf(someIndex);
```

## Combine arrays

```javascript
someArray.concat(anotherArray);
```

## Sort an array of numbers by value

```javascript
someNumbers.sort((a, b) => a - b);
```

## Get the largest number from an array of numbers

```javascript
Math.max(...someNumbers);
```

## Get the smallest number from an array of numbers

```javascript
Math.min(...someNumbers);
```

## Get all the keys from an object

```javascript
Object.keys(someObject);
```

## Divide a string from a separator search pattern

```javascript
someString.split(someSearchPattern);
```

## Combine strings with a separator search pattern

```javascript
someString.join(someSearchPattern);
```

## Replace search patterns in a string

```javascript
someString.replace(someSearchPattern, someReplacement);
```

## Find search patterns in a string

```javascript
someString.match(someSearchPattern);
```

## Get a character at a specific index in a string

```javascript
someString.charAt(someIndex);
```

## Convert the casing of a string to upper case

```javascript
someString.toUpperCase();
```

## Convert the casing of a string to lower case

```javascript
someString.toLowerCase();
```

## Repeat a string

```javascript
someString.repeat(someAmount);
```

For example:

```javascript
"a".repeat(4);
// "aaaa"
```

## Interpolate values in strings (template literals)

```javascript
`Some string with ${someValue} in it`;
```

## Convert a string into a number

```javascript
Number(someString);
```

For example:

```javascript
Number("123");
// 123
```

## Parse an integer inside a string

```javascript
parseInt(someString, radix);
```

For example:

```javascript
parseInt("123abc", 10);
// 123
```

## Extract data from a collection (destructuring)

```javascript
const { someKey } = someObject;
const [firstKey] = someArray;
```

## Extract data from a collection with remaining items grouped (rest)

```javascript
const { someKey, ...otherKeys } = someObject;
const [firstKey, ...otherKeys] = someArray;
```

## Expand data from a collection (spread)

```
{ someKey: someValue, ...someObject }
[ someValue, ...someArray ]
```

## Create a copy of a collection

```
{...someObject}
[...someArray]
```

## Use globals from the environment

```
[someEnvironment.]someGlobal
```

For example:

```javascript
// Output values to the console
console.log(someValue);
console.table(someTabularValue);

// Create assertions
console.assert(someExpression, "Some label");

// Send HTTP requests
await fetch(someUrl);

// Use HTTP request options
await fetch(someUrl, {
  method: 'some-http-method',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': Basic some-secret
  }
});

// Use HTTP request responses
const response = await fetch(someUrl);
if (response.status === some-http-status-code) {
  // ...
}

// Get JSON data from a JSON service
const response = await fetch(someUrl);
const json = await response.json();
```

## Use in a browser environment (HTML)

```html
<script type="module" src="/some-script.js"></script>
<noscript>Some script fallback</noscript>
```
