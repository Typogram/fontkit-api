# Subset Object

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It’s a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

Fontkit can perform font subsetting, i.e. the process of creating a new font from an existing font where only the specified glyphs are included. This is useful to reduce the size of large fonts, such

## Creating a Subset:

### `font.createSubset()`

* **Description**: Creates a new subset from the font.
* **Returns**: A new `Subset` object.

## Properties

### `subset.font`:

* **Type**: `Font`
* **Description**: The original font from which the subset is derived. It provides a reference to the main font object, allowing access to all its properties, methods, and associated data.

### `subset.glyphEncoder`:

* **Type**: Object or Encoder
* **Description**: The encoder responsible for encoding the glyphs when creating the subset. This will often handle the conversion of glyph data into the required format for the subset.

### `subset.glyphs`:

* **Type**: Array of `Glyph` objects
* **Description**: An array containing all the glyphs that are included in the subset. Each glyph is an instance of the `Glyph` object, encapsulating its individual properties, metrics, and path data.

### `subset.mapping`:

* **Type**: Object
* **Description**: Represents the mapping between the glyphs in the original font and their corresponding entries in the subset. This ensures that when text is rendered using the subset, the correct glyphs are displayed.

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
