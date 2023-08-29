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

### `glyph.id`

The unique identifier of the glyph in the font.

### `glyph.path`

A `Path` object representing the glyph's outline. This can be used to render the glyph or for other operations that involve the glyph's shape.

### `glyph.bbox`

The bounding box of the glyph, representing the rectangle that encloses the glyph's outline. It's an object with properties: `minX`, `minY`, `maxX`, and `maxY`.

### `glyph.cbox`

The control bounding box of the glyph. It's similar to the bounding box but includes bezier control points.

### `glyph.advanceWidth`

The advance width of the glyph, which is the amount the pen position should be moved after drawing the glyph.

### `glyph.advanceHeight`

The advance height of the glyph, indicating how much the pen position should move vertically after drawing the glyph (common in vertical writing modes).

### `glyph.codePoints`

An array of Unicode code points that the glyph represents.

## **Methods**:

### `glyph.getPath(x, y, fontSize)`

Returns a `Path` object for the glyph at the specified position (`x`, `y`) and size (`fontSize`). The `fontSize` parameter is optional and defaults to the font's units per em.

### `glyph.getMetrics()`

Retrieves metrics associated with the glyph, including the advance width, side bearings, and bounding box.

## **Advanced Properties (for specific font formats)**:

For TrueType fonts:

### `glyph.numberOfContours`

The number of contours in the glyph, which can be useful for some operations.

For CFF (Compact Font Format) fonts:

### `glyph.privateDict`

The private dictionary of the glyph, if available. CFF fonts can have specific settings and properties for individual glyphs stored in a private dictionary.

## **Render a Glyph's Path to SVG**:

```javascript
// Get a glyph for a specific code point (e.g., Unicode for "A")
const glyph = font.glyphForCodePoint(65);

// Convert the glyph's path to SVG
const svgPathData = glyph.path.toSVG();

console.log(`SVG Path Data for "A": ${svgPathData}`);
```
