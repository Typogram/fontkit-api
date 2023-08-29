# API Reference

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It's a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

## **Fontkit Object**

{% content-ref url="fontkit-object.md" %}
[fontkit-object.md](fontkit-object.md)
{% endcontent-ref %}

* `fontkit.openSync(filePath, postscriptName)` Opens a font file synchronously and returns a font object.
* `fontkit.open(filePath, postscriptName, callback)` Opens a font file asynchronously.
* `fontkit.create(buffer, postscriptName)` Creates a new font object from a buffer.

## **Font Object**

{% content-ref url="font-object.md" %}
[font-object.md](font-object.md)
{% endcontent-ref %}

* `font.layout(string)` Layouts the given string with the font and returns a GlyphRun object.
* `font.glyphForCodePoint(codePoint)` Gets a glyph for a given Unicode code point.
* `font.hasGlyphForCodePoint(codePoint)` Checks if the font has a glyph for the given code point.
* `font.characterSet` Returns the set of Unicode code points supported by the font.
* `font.availableFeatures` Returns the list of OpenType feature tags available in the font.

## **GlyphRun Object**

{% content-ref url="glyphrun-object.md" %}
[glyphrun-object.md](glyphrun-object.md)
{% endcontent-ref %}

* `glyphRun.glyphs` An array of Glyph objects in the run.
* `glyphRun.positions` An array of position objects for each glyph.
* `glyphRun.stringIndices` An array of original string indices for each glyph.

## **Glyph Object**

{% content-ref url="glyph-object.md" %}
[glyph-object.md](glyph-object.md)
{% endcontent-ref %}

* `glyph.path` Returns a Path object representing the glyph’s outline.
* `glyph.bbox` Gets the glyph’s bounding box, i.e., the rectangle that encloses the glyph’s outline.
* `glyph.cbox` Gets the glyph’s control bounding box.
* `glyph.advanceWidth` The advance width of the glyph.

## **Path Object**

{% content-ref url="path-object.md" %}
[path-object.md](path-object.md)
{% endcontent-ref %}

* `path.moveTo(x, y)` Moves the pen to a new location.
* `path.lineTo(x, y)` Draws a straight line to a new location.
* `path.curveTo(cp1x, cp1y, cp2x, cp2y, x, y)` Draws a cubic bezier curve.
* `path.qcurveTo(cpx, cpy, x, y)` Draws a quadratic bezier curve.
* `path.closePath()` Closes the current path.
* `path.bbox` Returns the bounding box of the path.

## Subset Object

{% content-ref url="subset-object.md" %}
[subset-object.md](subset-object.md)
{% endcontent-ref %}

* `subset.includeGlyph(glyph)` Includes the given glyph in the subset.
* `subset.encode()` Encodes the subset font.
