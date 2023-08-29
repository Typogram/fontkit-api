---
description: >-
  The main `fontkit` object is the entry point to the library and provides
  methods for opening and reading font files. Here's a detailed look at the
  `fontkit` object's methods and properties:
---

# Fontkit Object

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It's a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

## **Methods**:

### `fontkit.openSync(filePath, postscriptName)`

* **Description**: Opens a font file synchronously and returns a `Font` object.
* **Parameters**:
  * `filePath`: The path to the font file.
  * `postscriptName`: (Optional) The specific font to load in case the file contains multiple fonts.

### `fontkit.open(filePath, postscriptName, callback)`

* **Description**: Opens a font file asynchronously.
* **Parameters**:
  * `filePath`: The path to the font file.
  * `postscriptName`: (Optional) The specific font to load in case the file contains multiple fonts.
  * `callback`: Function to be called once the font is loaded. It follows the typical node callback pattern where the first argument is an error, and the second is the resulting `Font` object.

### `fontkit.create(buffer, postscriptName)`

* **Description**: Creates a new `Font` object from a buffer. This is useful if you've already read the font file into memory or if you're retrieving it from a source other than the file system.
* **Parameters**:
  * `buffer`: A buffer containing the font data.
  * `postscriptName`: (Optional) The specific font to load in case the buffer contains multiple fonts.

## **Properties**:

As of my last update in September 2021, the primary interactions with the `fontkit` object are through the methods listed above. There aren't specific notable properties directly on the `fontkit` object itself; most of the functionality and properties you'd interact with are on the objects it returns (like the `Font` object).

## **Supported Font Formats**:

Fontkit is known for its comprehensive support for different font formats. While this isn't directly a method or property on the `fontkit` object, it's worth noting that Fontkit supports formats like:

* TrueType (`ttf`)
* OpenType (`otf`)
* WOFF & WOFF2
* TrueType Collection (`ttc`)
* Datafork TrueType Suite (`dfont`)
* And more...

## **Use fontkit in browser context**:

```
npm install fontkit
```

```javascript
import * as fontkit from 'fontkit';

const response = await fetch(url);
const arrayBuffer = await response.arrayBuffer();
const buf = new Uint8Array(arrayBuffer);
const font = fontkit.create(buf);
```
