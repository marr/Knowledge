# HTML

## Learn more

- https://html.spec.whatwg.org/

## Create a document

```
<!DOCTYPE html>

<html lang="some-language">
  <head>
    ...
  </head>

  <body>
    ...
  </body>
</html>
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

## Create a section that holds the primary content

```
<main>...</main>
```

## Create a section that holds content indirectly related to the primary content

```
<aside>...</aside>
```

## Create a section that holds navigation links

```
<nav>...</nav>
```

## Create a section that holds introductory content

```
<header>...</header>
```

## Create a section that holds meta data content related to the section it is in

```
<footer>...</footer>
```

## Create a section that holds a self-contained composition for things like syndication

```
<article>...</article>
```

## Create a generic section that doesn't have a more specific semantic element

```
<section>...</section>
```

## Create headings

```
<h1>Some label</h1>
<h2>Some label</h2>
<h3>Some label</h3>
<h4>Some label</h4>
<h5>Some label</h5>
<h6>Some label</h6>
```

## Create a paragraph

```html
<p>Some content</p>
```

## Create a list of items

```html
<ul>
  <li>Some label</li>
  <li>Some label</li>
</ul>
```

## Create a list of items that are in order

```html
<ol>
  <li>Some label</li>
  <li>Some label</li>
</ol>
```

## Create a link

```
<a href="some-path" [download]>Some label</a>
```

- Email path: `mailto:{some-email}?subject={some-subject}&body={some-body}`.
- Call path: `tel:{some-phone}`.
- SMS path: `sms:{some-phone}?body={some-body}`.

## Create clickable actions

```html
<button>Some label</button>
```

## Create interactive controls for submitting information

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

## Create an accordion

```
<details>
  <summary>Some label</summary>
  ...
</details>
```

## Create a modal

```
<dialog open>...</dialog>
```

## Create an embedded image

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

## Create an embedded audio player

```
<audio src="some-path" ...>Some description</audio>
```

## Create an embedded video player

```
<video src="some-path" ...>Some description</video>
```

## Create an embedded web page

```html
<iframe src="some-path" loading="lazy"></iframe>
```

## Create an embedded PDF

```html
<object type="application/pdf" data="some-path"></object>
```

## Create programmatic graphics

```html
<canvas>Some description </canvas>
```

## Create columns and rows of tabular data

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

## Create text with additional importance

```html
<strong>Some text</strong>
```

## Create text representing a specific time

```html
<time datetime="some-machine-readable-format">Some label</time>
```

## Create a quote

```html
<blockquote>Some quote</blockquote>
```

## Create self-contained content

```html
<figure>
  Some content
  <figcaption>Some description</figcaption>
</figure>
```

## Create a forced line-break

```html
<br />
```

## Create text that contains programming code

```html
<code>some-code</code>
```

## Create text that retains the formatting used in the source

```html
<pre>some-text</pre>
```

## Create side comments

```html
<small>some-text</small>
```
