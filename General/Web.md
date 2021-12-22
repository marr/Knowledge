# Web

## Learn more

- https://developer.mozilla.org/en-US/docs/Web

## Communicate between web browsers and web servers

```
HTTP
```

###  Retrieve data

```
GET
```

###  Submit data

```
POST
```

###  Replace data

```
PUT
```

###  Remove data

```
DELETE
```

###  Indicate the result of a request in the response

```
Status code
```

- 100–199 for informational responses.
- 200–299 for successful responses.
- 300–399 for redirects.
- 400–499 for client errors.
- 500–599 for server errors.
- `200` is a catchall for success.
- `404` means the requested resource is not available.
- `403` means the requester does not have permission to access the requested resource.
- `500` is a catchall for server-side errors.

###  Include additional information in headers of requests or responses

```
Name: value
```

For example:

```
Cache-Control: max-age=600
Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l
Age: 24
```

## Create web documents

```
HTML
```

For example:

```html
<!DOCTYPE html>

<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>Some title</title>
    <meta name="description" content="Some description" />
    <meta name="author" content="Some author" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link rel="stylesheet" href="/some-style.css" />
    <script type="module" src="/some-script.js"></script>
    <noscript>Some script fallback</noscript>
  </head>

  <body>
    <header>
      <h1>Some heading</h1>
      <nav>
        <a href="/">Some page</a>
        <a href="/another/">Another page</a>
      </nav>
    </header>

    <main>
      <h2>Some heading</h2>
      <p>Some paragraph</p>
    </main>
  </body>
</html>
```

###  Create a section that holds the primary content

```
<main>...</main>
```

###  Create a section that holds content indirectly related to the primary content

```
<aside>...</aside>
```

###  Create a section that holds navigation links

```
<nav>...</nav>
```

###  Create a section that holds introductory content

```
<header>...</header>
```

###  Create a section that holds meta data content related to the section it is in

```
<footer>...</footer>
```

###  Create a section that holds a self-contained composition for things like syndication

```
<article>...</article>
```

###  Create a generic section that doesn't have a more specific semantic element

```
<section>...</section>
```

###  Create headings

```
<h1>Some label</h1>
<h2>Some label</h2>
<h3>Some label</h3>
<h4>Some label</h4>
<h5>Some label</h5>
<h6>Some label</h6>
```

###  Create a paragraph

```html
<p>Some content</p>
```

###  Create a list of items

```html
<ul>
  <li>Some label</li>
  <li>Some label</li>
</ul>
```

###  Create a list of items that are in order

```html
<ol>
  <li>Some label</li>
  <li>Some label</li>
</ol>
```

###  Create a link

```
<a href="some-path" [download]>Some label</a>
```

- Email path: `mailto:{some-email}?subject={some-subject}&body={some-body}`.
- Call path: `tel:{some-phone}`.
- SMS path: `sms:{some-phone}?body={some-body}`.

###  Create clickable actions

```html
<button>Some label</button>
```

###  Create interactive controls for submitting information

```
<form>
  ...
</form>
```

For example:

```
<form>
  <label for="some-id">Some label</label>
  <input
    id="some-id"
    type="{number/tel/url/email/date/password/file/color/radio/checkbox/range/text}"
    required
    pattern="some-search-pattern"
    ...
  />
</form>

<form>
  <label for="some-id">Some label</label>
  <textarea id="some-id" />
</form>

<form>
  <select>
    <option>Some label</option>
    <option>Some label</option>
  </select>
</form>

<form>
  <label for="some-id">Some label</label>
  <input list="list-id" id="some-id" />
  <datalist id="list-id">
    <option>Some label</option>
    <option>Some label</option>
  </datalist>
</form>

<form>
  <label for="some-id">Some label</label>
  <progress id="some-id" max="100" value="70">Some label</progress>
</form>

<form>
  <label for="some-id">Some label</label>
  <meter id="some-id" min="0" max="100" low="25" high="50" optimum="75" value="90"></meter>
</form>
```

###  Create an accordion

```
<details>
  <summary>Some label</summary>
  ...
</details>
```

###  Create a modal

```
<dialog open>...</dialog>
```

###  Create an embedded image

```
<picture>
  <source srcset="some-path some-size, another-path another-size" type="image/some-type" />
  <source srcset="some-path some-size, another-path another-size" type="image/another-type" />
  <img src="some-path" alt="Some description" loading="lazy" />
</picture>

<img
  srcset="some-path some-size, another-path another-size"
  src="some-path"
  alt="Some description"
  loading="lazy"
/>
```

For example:

```html
<picture>
  <source srcset="https://via.placeholder.com/300x100.webp 300w, https://via.placeholder.com/600x200.webp 600w, https://via.placeholder.com/1200x400.webp 1200w" type="image/webp" />
  <source srcset="https://via.placeholder.com/300x100.jpeg 300w, https://via.placeholder.com/600x200.jpeg 600w, https://via.placeholder.com/1200x400.jpeg 1200w" type="image/jpeg" />
  <img src="https://via.placeholder.com/300x100.jpeg" alt="An apple tree" loading="lazy" />
</picture>

<img
  srcset="https://via.placeholder.com/300x100.webp 300w, https://via.placeholder.com/600x200.webp 600w, https://via.placeholder.com/1200x400.webp 1200w"
  src="https://via.placeholder.com/300x100.webp"   alt="An apple tree"
  loading="lazy"
/>
```

###  Create an embedded audio player

```
<audio src="some-path" ...>Some description</audio>
```

###  Create an embedded video player

```
<video src="some-path" ...>Some description</video>
```

###  Create an embedded web page

```html
<iframe src="some-path" loading="lazy"></iframe>
```

###  Create an embedded PDF

```html
<object type="application/pdf" data="some-path"></object>
```

###  Create programmatic graphics

```html
<canvas>Some description </canvas>
```

###  Create columns and rows of tabular data

```html
<table>
  <thead>
    <tr>
      <th>Some header</th>
      <th>Some header</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Some data</td>
      <td>Some data</td>
    </tr>
  </tbody>
</table>
```

###  Create text with additional importance

```html
<strong>Some text</strong>
```

###  Create text representing a specific time

```html
<time datetime="some-machine-readable-format">Some label</time>
```

###  Create a quote

```html
<blockquote>Some quote</blockquote>
```

###  Create self-contained content

```html
<figure>
  Some content
  <figcaption>Some description</figcaption>
</figure>
```

###  Create a forced line-break

```html
<br />
```

###  Create text that contains programming code

```html
<code>some-code</code>
```

###  Create text that retains the formatting used in the source

```html
<pre>some-text</pre>
```

###  Create side comments

```html
<small>some-text</small>
```

## Change the presentation of web documents

```
CSS
```

###  Align items in a row vertically

```
some-selector {
  display: flex;
  align-items: center;
}
```

###  Add animation between changes

```
transition: X.Ys;
```

For example:

```css
a,
a:visited {
  color: LightSeaGreen;
  transition: 0.3s;
}

a:hover,
a:focus {
  opacity: 0.7;
}
```

## Add functionality to web documents

```
JavaScript
```

###  Create APIs that can be shared across files (modules)

```
export default someThing
export anotherThing
```

###  Use APIs that are shared across files (modules)

```
import someThing, { anotherThing } from "some-path";
await import("some-path");
```

###  Create functions

```
(someParameter) => ...
```

###  Use a default value for function parameters

```
(someParameter = someValue) => ...
```

###  Create asynchronous functions that return an unresolved value (promise)

```
async (someParameter) => ...
```

###  Use asynchronous functions that return an unresolved value (promise)

```
await someFunction();
```

###  Apply a function on every item in an array

```
someArray.map(someItem => // return updated item)
```

###  Get items in an array that meet a condition

```
someArray.filter(someItem => // return boolean for the condition)
```

###  Check if all items in an array meet a condition

```
someArray.every(someItem => // return boolean for the condition)
```

###  Check if at least one item in an array meets a condition

```
someArray.some(someItem => // return boolean for the condition)
```

###  Get the first item in an array that meets a condition

```
someArray.find(someItem => // return boolean for the condition)
```

###  Convert an array to a single value

```
someArray.reduce((someAccumulation, someItem)  => // return accumulation, someInitialValue)
```

###  Get whether an array contains a value

```javascript
someArray.includes(someValue);
```

###  Remove falsy values from an array

```javascript
someArray.filter((someItem) => !!someItem);
```

###  Sort an array

```javascript
someArray.sort();
```

###  Reverse an array

```javascript
[...someArray].reverse();
```

###  Get the unique items in an array

```javascript
[...new Set(someArray)];
```

###  Get a portion of an array by index

```javascript
someArray.slice(someStartIndex, someEndIndex);
```

###  Get the index of an item in an array

```javascript
someString.indexOf(someIndex);
```

###  Combine arrays

```javascript
someArray.concat(anotherArray);
```

###  Sort an array of numbers by value

```javascript
someNumbers.sort((a, b) => a - b);
```

###  Get the largest number from an array of numbers

```javascript
Math.max(...someNumbers);
```

###  Get the smallest number from an array of numbers

```javascript
Math.min(...someNumbers);
```

###  Get all the keys from an object

```javascript
Object.keys(someObject);
```

###  Divide a string from a separator search pattern

```javascript
someString.split(someSearchPattern);
```

###  Combine strings with a separator search pattern

```javascript
someString.join(someSearchPattern);
```

###  Replace search patterns in a string

```javascript
someString.replace(someSearchPattern, someReplacement);
```

###  Find search patterns in a string

```javascript
someString.match(someSearchPattern);
```

###  Get a character at a specific index in a string

```javascript
someString.charAt(someIndex);
```

###  Convert the casing of a string to upper case

```javascript
someString.toUpperCase();
```

###  Convert the casing of a string to lower case

```javascript
someString.toLowerCase();
```

###  Repeat a string

```javascript
someString.repeat(someAmount);
```

For example:

```javascript
"a".repeat(4);
// "aaaa"
```

###  Interpolate values in strings (template literals)

```javascript
`Some string with ${someValue} in it`;
```

###  Convert a string into a number

```javascript
Number(someString);
```

For example:

```javascript
Number("123");
// 123
```

###  Parse an integer inside a string

```javascript
parseInt(someString, radix);
```

For example:

```javascript
parseInt("123abc", 10);
// 123
```

###  Extract data from a collection (destructuring)

```javascript
const { someKey } = someObject;
const [firstKey] = someArray;
```

###  Extract data from a collection with remaining items grouped (rest)

```javascript
const { someKey, ...otherKeys } = someObject;
const [firstKey, ...otherKeys] = someArray;
```

###  Expand data from a collection (spread)

```
{ someKey: someValue, ...someObject }
[ someValue, ...someArray ]
```

###  Create a copy of a collection

```
{...someObject}
[...someArray]
```

###  Use browser globals

```
[someGlobal.]someThing
```

For example:

```javascript
// Output values to the console
console.log(someValue);
console.table(someTabularValue);

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
