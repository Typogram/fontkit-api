---
description: >-
  The `GlyphRun` object in Fontkit represents a sequence of glyphs and their
  associated positions. When you layout a string using the `font.layout()`
  method, it returns a `GlyphRun` object.
---

# GlyphRun Object

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It's a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

## **Properties**:

### `glyphRun.glyphs`:

* **Description**: An array of `Glyph` objects representing the individual glyphs in the run.
* **Type**: Array of `Glyph` objects

### `glyphRun.positions`:

* **Description**: An array of position objects, where each position corresponds to the `Glyph` at the same index in the `glyphs` array. Each position object typically contains `x` and `y` offsets and an advance width and height.
* **Type**: Array of Position Objects. Each position object has properties:
  * `xAdvance`: The amount to move the pen in the x-direction after drawing the glyph.
  * `yAdvance`: The amount to move the pen in the y-direction after drawing the glyph.
  * `xOffset`: The x offset to apply when drawing this glyph.
  * `yOffset`: The y offset to apply when drawing this glyph.

### `glyphRun.features`:

* **Description**: An array of OpenType feature tags applied to this run, which can affect the final set of glyphs and their positions.
* **Type**: Array of Strings

### `glyphRun.script`:

* **Description**: The script (or writing system) used for this run of text, as determined by the shaping engine.
* **Type**: String

### `glyphRun.language`:

* **Description**: The language tag for this run of text, which can affect shaping in some scripts.
* **Type**: String

### `glyphRun.direction`:

* **Description**: The text direction for this run. Common values include 'ltr' (left-to-right) and 'rtl' (right-to-left).
* **Type**: String

### `glyphRun.advanceWidth`:

* **Description**: The total advance width of the glyph run. This is the sum of the horizontal advances of all the glyphs in the run, and it represents the width that the glyph run would occupy if rendered.
* **Type**: Number

### `glyphRun.advanceHeight`:

* **Description**: The total advance height of the glyph run. This is particularly relevant for vertical text layouts.
* **Type**: Number

### `glyphRun.bbox`:

* **Description**: The bounding box of the glyph run. It encompasses all the glyphs in the run and provides `minX`, `minY`, `maxX`, and `maxY` properties.
* **Type**: Object

## **Methods**:

The main interaction with a `GlyphRun` object revolves around accessing its properties rather than calling methods. Most of the manipulation or querying one would do with the `GlyphRun` results involves working directly with the properties listed above. For instance, iterating over the glyphs or positions to perform certain tasks or calculations.
