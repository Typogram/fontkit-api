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

### `glyphRun.glyphs`

An array of `Glyph` objects in the run. Each glyph corresponds to a specific visual representation in the font for a character or a sequence of characters in the input text.

### `glyphRun.positions`

An array of position objects for each glyph. Each position object has two properties:

* `xAdvance`: The amount to move the pen in the x-direction after drawing the glyph.
* `yAdvance`: The amount to move the pen in the y-direction after drawing the glyph.
* `xOffset`: The x offset to apply when drawing this glyph.
* `yOffset`: The y offset to apply when drawing this glyph.

### `glyphRun.stringIndices`

An array of original string indices for each glyph. This maps each glyph back to a position in the original string. This can be useful for various tasks, such as cursor positioning or text selection in complex scripts where one character can map to multiple glyphs or vice versa.

### `glyphRun.features`

The OpenType features that were applied when creating the glyph run.

## **Methods**:

The main interaction with a `GlyphRun` object revolves around accessing its properties rather than calling methods. Most of the manipulation or querying one would do with the `GlyphRun` results involves working directly with the properties listed above. For instance, iterating over the glyphs or positions to perform certain tasks or calculations.
