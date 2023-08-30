# Glyph Object

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It’s a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

The `Glyph` object in Fontkit represents an individual glyph in the font, which corresponds to a specific visual representation of one or more characters.

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

### `glyph_getPath()`:

* **Description**: (Internal) Retrieves the path data for the glyph, which can be used for rendering or other operations.
* **Returns**: A `Path` object representing the glyph's outlines.

### `glyph_getMetrics()`:

* **Description**: (Internal) Retrieves the metrics for the glyph, which define its layout characteristics.
* **Returns**: Metrics data.

### `glyph_getContours()`:

* **Description**: (Internal) Retrieves the contours of the glyph, which define the glyph's shape.
* **Returns**: An array of contours.

### `glyph_getCBox()`:

* **Description**: (Internal) Retrieves the control bounding box of the glyph. This box encompasses all control points of the glyph's path.
* **Returns**: Object

### `glyph_getPhantomPoints(glyph)`:

* **Description**: (Internal) Retrieves the phantom points for the glyph, which are often used for hinting and layout purposes.
* **Returns**: An array of phantom points.

### `glyph_parseGlyphCoord(stream, prev, short, same)`:

* **Description**: (Internal) Parses specific coordinates from the glyph data, often used in the decoding process.
* **Parameters**: Typically involves parameters related to font data or encoding specifics.
* **Returns**: Parsed coordinates (usually Numbers or Objects).

### `glyph_decode()`:

* **Description**: (Internal) Decodes the glyph data, which can be either simple or composite, depending on the glyph type.
* **Parameters**: Typically data or stream references from the font file.
* **Returns**: Decoded glyph data.

### `glyph_decodeSimple(glyph, stream):`

* **Description**: (Internal) Decodes the data for a simple glyph type.
* **Parameters**: Typically data or stream references from the font file.
* **Returns**: Decoded simple glyph data.

### `glyph_decodeComposite(glyph, stream, offset = 0):`

* **Description**: (Internal) Decodes the data for a composite glyph type.
* **Parameters**: Typically data or stream references from the font file.
* **Returns**: Decoded composite glyph data.

## **Render a Glyph's Path to SVG**:

```javascript
// Get a glyph for a specific code point (e.g., Unicode for "A")
const glyph = font.glyphForCodePoint(65);

// Convert the glyph's path to SVG
const svgPathData = glyph.path.toSVG();

console.log(`SVG Path Data for "A": ${svgPathData}`);
```
