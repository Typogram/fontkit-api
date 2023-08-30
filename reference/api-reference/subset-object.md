# Subset Object

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It’s a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

Fontkit can perform font subsetting, i.e. the process of creating a new font from an existing font where only the specified glyphs are included. This is useful to reduce the size of large fonts, such

## Creating a Subset:

### `font.createSubset()`

* **Description**: Creates a new subset from the font.
* **Returns**: A new `Subset` object.

## Methods:

### `subset.includeGlyph(glyph)`

* **Description**: Includes the given glyph in the subset.
* **Parameters**:
  * `glyph`: A `Glyph` object or glyph ID to be included in the subset.

### `subset.encode()`

* **Description**: Encodes the subset font.
* **Returns**: A `Uint8Array` containing the encoded font data.

## Example:

```javascript
// Create a new subset
const subset = font.createSubset();

// Include glyphs for the string "Hello, World!"
for (const char of 'Hello, World!') {
  const glyph = font.glyphForCodePoint(char.codePointAt(0));
  subset.includeGlyph(glyph);
}

// Encode the subset into a Uint8Array
const subsetData = subset.encode();

// The resulting subsetData can be used for embedding in a PDF or other purposes.
```
