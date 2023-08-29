---
description: >-
  The `Glyph` object in Fontkit represents an individual glyph in the font,
  which corresponds to a specific visual representation of one or more
  characters.
---

# Glyph Object

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It's a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

## **Properties**:

### `glyph.id`:

* **Description**: A unique identifier for the glyph within its font.
* **Type**: Number

### `glyph.path`:

* **Description**: The path object for the glyph, representing the glyph's outlines and can be rendered or used for various operations.
* **Type**: `Path` object

### `glyph.name`:

* **Description**: The name of the glyph, which can be a standard glyph name or a custom one defined by the font creator.
* **Type**: String

### `glyph.type`:

* **Description**: The type of glyph, such as 'simple' or 'composite'.
* **Type**: String

### `glyph.codePoints`:

* **Description**: An array of Unicode code points that the glyph represents. This can be more than one for ligatures and other combined forms.
* **Type**: Array of Numbers

### `glyph.advanceWidth`:

* **Description**: The advance width of the glyph, representing the space the glyph occupies horizontally.
* **Type**: Number

### `glyph.advanceHeight`:

* **Description**: The advance height of the glyph, representing the vertical space the glyph occupies. Relevant for vertical text layouts.
* **Type**: Number

### `glyph.bbox`:

* **Description**: The bounding box of the glyph, encompassing the entire glyph and providing `minX`, `minY`, `maxX`, and `maxY` properties.
* **Type**: Object

### `glyph.cbox`:

* **Description**: The control bounding box of the glyph, which encompasses all control points of the glyph's path. Useful for some precise layout operations.
* **Type**: Object

### `glyph.isMark`:

* **Description**: Indicates if the glyph is a mark glyph, which is used for combining characters in many scripts.
* **Type**: Boolean

### `glyph.isLigature`:

* **Description**: Indicates if the glyph is a ligature, representing multiple characters combined into a single glyph.
* **Type**: Boolean

### `glyph.ligatureCaretPositions`:

* **Description**: An array indicating positions within the glyph where carets should be drawn when the glyph is selected. Relevant for ligatures where multiple characters combine into a single glyph.
* **Type**: Array of Numbers

### `glyph._font`:

* **Description**: (Internal) Reference to the font object the glyph belongs to.
* **Type**: `Font` object

### `glyph._metrics`:

* **Description**: (Internal) Metrics data for the glyph. Typically used internally by Fontkit.
* **Type**: Object

## **Methods**:

### `glyph._getPath(x, y, fontSize)`

Returns a `Path` object for the glyph at the specified position (`x`, `y`) and size (`fontSize`). The `fontSize` parameter is optional and defaults to the font's units per em.

### `glyph._getMetrics()`

Retrieves metrics associated with the glyph, including the advance width, side bearings, and bounding box.

## **Render a Glyph's Path to SVG**:

```javascript
// Get a glyph for a specific code point (e.g., Unicode for "A")
const glyph = font.glyphForCodePoint(65);

// Convert the glyph's path to SVG
const svgPathData = glyph.path.toSVG();

console.log(`SVG Path Data for "A": ${svgPathData}`);
```
