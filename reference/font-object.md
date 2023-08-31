# Font Object

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It’s a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

The Font object is central to Fontkit. It represents a font in your system or a font file.

## Properties (Read-only)

### `font.postscriptName`:

* **Description**: The PostScript name of the font. This is a unique identifier, often used in CSS and other contexts.
* **Type**: String

### `font.fullName`:

* **Description**: The full name of the font, typically including its weight or style.
* **Type**: String

### `font.familyName`:

* **Description**: The name of the font family to which this font belongs.
* **Type**: String

### `font.subfamilyName`:

* **Description**: The specific style or weight of the font within its family (e.g., "Bold" or "Italic").
* **Type**: String

### `font.copyright`:

* **Description**: The copyright statement associated with the font.
* **Type**: String

### `font.version`:

* **Description**: The version string of the font.
* **Type**: String

***

### `font.numGlyphs`:

* **Description**: The total number of glyphs in the font.
* **Type**: Number

### `font.characterSet`:

* **Description**: A set of all Unicode characters covered by the font.
* **Type**: Set of Numbers

### `font.availableFeatures`:

* **Description**: A list of OpenType feature tags available in the font.
* **Type**: Array of Strings

***

### `font.unitsPerEm`:

* **Description**: The number of font units per em. It's a foundational metric for a font, often set to values like 1000 or 2048.
* **Type**: Number

### `font.ascent`:

* **Description**: The font's ascent, which is the distance from the baseline to the top of the font's bounding box.
* **Type**: Number

### `font.descent`:

* **Description**: The font's descent, which is the distance from the baseline to the bottom of the font's bounding box.
* **Type**: Number

### `font.capHeight`:

* **Description**: The height of capital letters from the baseline.
* **Type**: Number

### `font.xHeight`:

* **Description**: The height of lowercase letters, specifically the height of the letter 'x'.
* **Type**: Number

### `font.lineGap`:

* **Description**: The recommended line gap or spacing between lines of text for this font.
* **Type**: Number

### `font.underlinePosition`:

* **Description**: The position of the underline relative to the baseline.
* **Type**: Number

### `font.underlineThickness`:

* **Description**: The thickness of the underline.
* **Type**: Number

### `font.italicAngle`:

* **Description**: The angle (in degrees) of the italic slant. Upright fonts have an italic angle of 0.
* **Type**: Number

### `font.bbox`:

* **Description**: The font's bounding box, which encompasses all glyphs in the font. It's an object with `minX`, `minY`, `maxX`, and `maxY` properties.
* **Type**: Object

***

### `font.variationAxes`:

* **Description**: Information about variable font axes if the font is a variable font. Each axis has properties like `tag`, `name`, `min`, `default`, and `max`.
* **Type**: Array of Objects

### `font.namedVariations`:

* **Description**: Named instances for variable fonts, such as predefined width or weight variations.
* **Type**: Object

***

### `font._cmapProcessor`:

* **Description**: An internal processor for the font's character map. Typically used internally by Fontkit.
* **Type**: Object

### `font._layoutEngine`:

* **Description**: An internal engine for glyph layout. Typically used internally by Fontkit.
* **Type**: Object

### `font._variationProcessor`:

* **Description**: An internal processor for handling font variations. Typically used internally by Fontkit.
* **Type**: Object

## Other Properties

### Basic properties:

<table><thead><tr><th width="155">Property</th><th>Description</th></tr></thead><tbody><tr><td><code>.type</code></td><td>The type of the font, such as 'truetype', 'cff', etc.</td></tr><tr><td><code>.defaultLanguage</code></td><td>The default language for the font, used when retrieving names and other language-specific details.</td></tr><tr><td><code>.stream</code></td><td>The readable stream from which the font is being read. Useful for reading binary data directly from the font file.</td></tr><tr><td><code>.variationCoords</code></td><td>An object representing the coordinates for variable font instances. If the font is not variable, this property is null.</td></tr><tr><td><code>._directoryPos</code></td><td>(Internal) Position of the directory within the font stream. Typically used internally by Fontkit for navigation purposes.</td></tr><tr><td><code>._tables</code></td><td>(Internal) A cache of parsed tables. Used internally by Fontkit to store tables that have been parsed.</td></tr><tr><td><code>._glyphs</code></td><td>(Internal) A cache of parsed glyphs. Used internally by Fontkit to store glyphs that have been read from the font.</td></tr><tr><td><code>.directory</code></td><td>The font's directory table, which provides an index to the rest of the tables in the font.</td></tr></tbody></table>

### Font tables as properties:

<table><thead><tr><th width="111">Property</th><th>Description</th></tr></thead><tbody><tr><td><code>.GDEF</code></td><td>Glyph Definition Table: Contains glyph class definitions, ligature caret lists, and glyph attachment positioning.</td></tr><tr><td><code>.GPOS</code></td><td>Glyph Positioning Table: Contains information about positioning glyphs in complex scripts or ligature adjustments.</td></tr><tr><td><code>.GSUB</code></td><td>Glyph Substitution Table: Defines glyph substitutions, such as ligatures, contextual alternates, etc.</td></tr><tr><td><code>.OS/2</code></td><td>OS/2 and Windows Specific Table: Contains metrics, glyph index ranges, style flags, and other font metadata.</td></tr><tr><td><code>.cmap</code></td><td>Character to Glyph Index Mapping Table: Maps character codes to glyph indices.</td></tr><tr><td><code>.cvt</code></td><td>Control Value Table: Contains values used by the fpgm table and the glyf table for hinting.</td></tr><tr><td><code>.fpgm</code></td><td>Font Program: Contains hinting instructions for the font.</td></tr><tr><td><code>.gasp</code></td><td>Grid-fitting and Scan-conversion Procedure Table: Contains information for grid-fitting and anti-aliasing.</td></tr><tr><td><code>.glyf</code></td><td>Glyph Data Table: Contains the outlines of the glyphs in the font.</td></tr><tr><td><code>.head</code></td><td>Font Header Table: Contains global font information such as bounding box, version, etc.</td></tr><tr><td><code>.hhea</code></td><td>Horizontal Header Table: Contains horizontal metrics and settings.</td></tr><tr><td><code>.hmtx</code></td><td>Horizontal Metrics Table: Contains metrics for each glyph's horizontal layout.</td></tr><tr><td><code>.loca</code></td><td>Index to Location Table: Contains offsets to each glyph in the <code>glyf</code> table.</td></tr><tr><td><code>.maxp</code></td><td>Maximum Profile Table: Contains the maximum values for various font-wide parameters.</td></tr><tr><td><code>.name</code></td><td>Naming Table: Contains names for various font attributes, including designer, copyright, etc.</td></tr><tr><td><code>.post</code></td><td>PostScript Table: Contains information used for emulating PostScript fonts.</td></tr><tr><td><code>.prep</code></td><td>Control Value Program: Contains hinting instructions executed before processing any glyph in the font.</td></tr></tbody></table>

## **Methods**:

### `font.createSubset()`:

* **Description**: Creates a `Subset` object, allowing you to create a new font containing only specified glyphs.
* **Returns**: `Subset` object for further operations.

### `font.getAvailableFeatures()`:

* **Description**: Lists the OpenType layout features available in the font.
* **Returns**: Array of available feature tags.

### `font.getFont()`:

* **Description**: If the font file contains multiple fonts, retrieves a specific one.
* **Parameters**: Index or specific criteria for font selection.
* **Returns**: `Font` object.

### `font.getGlyph()`:

* **Description**: Retrieves a glyph by its ID.
* **Parameters**: Glyph ID.
* **Returns**: Corresponding `Glyph` object.

### `font.getVariation(variation)`:

* **Description**: Returns a new Font object for the given variation.
* **Parameters**: Variation criteria or name.
* **Returns**: Variation data.

### `font.glyphForCodePoint(codePoint)`:

* **Description**: Returns a `Glyph` object for a given Unicode code point.
* **Parameters**: Unicode code point.
* **Returns**: Corresponding `Glyph` object.

### `font.glyphsForString(string)`:

* **Description**: Returns an array of `Glyph` objects for a given string.
* **Parameters**: A string of characters.
* **Returns**: Array of `Glyph` objects.

### `font.hasGlyphForCodePoint(codePoint)`:

* **Description**: Checks if the font has a glyph for the given Unicode code point.
* **Parameters**: Unicode code point.
* **Returns**: Boolean indicating presence of the glyph.

### `font.layout(text, features, script, language)`:

* **Description**: This is used to lay out a string of text, returning a `GlyphRun` object. The `features` parameter is optional and can be used to turn on or off OpenType features. The `script` and `language` parameters can be used to set the script and language for shaping.
* **Parameters**: A string of characters, and potentially additional layout parameters.
* **Returns**: `GlyphRun` object.

### `font.getName()`:

* **Description**: Retrieves the human-readable name for a specific name ID in the font.
* **Parameters**: Name ID.
* **Returns**: String representing the name.

### `font.setDefaultLanguage()`:

* **Description**: Sets the default language for the font, affecting layout operations.
* **Parameters**: Language tag.
* **Returns**: Void (changes are applied to the `Font` object).

### `font.stringsForGlyph()`:

* **Description**: Retrieves strings that map to a specific glyph.
* **Parameters**: Glyph ID or `Glyph` object.
* **Returns**: Array of strings.

### `font._decodeDirectory()`:

* **Description**: (Internal) Decodes the directory structure of the font, which is a key part of its binary data.
* **Parameters**: Typically involves references or offsets from the font file.
* **Returns**: Decoded directory structure.

### `font._decodeTable()`:

* **Description**: (Internal) Decodes a specific table from the font's binary data.
* **Parameters**: Table references or names from the font file.
* **Returns**: Decoded table data.

### `font._getBaseGlyph()`:

* **Description**: (Internal) Retrieves the base glyph for a particular character or code point.
* **Parameters**: Usually a character or code point.
* **Returns**: Corresponding base `Glyph` object.

### `font._getTable()`:

* **Description**: (Internal) Fetches a specific table from the font.
* **Parameters**: Table name or reference.
* **Returns**: Table data.

### `font._getTableStream()`:

* **Description**: (Internal) Retrieves a stream for reading a specific table from the font's binary data.
* **Parameters**: Table name or reference.
* **Returns**: Data stream for the specified table.

## **Layout a String and Access Glyphs**:

```javascript
const run = font.layout('Hello, Fontkit!');

// Iterate over each glyph in the GlyphRun to put together pathData
let pathData = '';
let x = 0;
let y = 0;
run.glyphs.forEach((glyph, index) => {
  console.log(`Glyph ID: ${glyph.id}, Unicode: ${String.fromCodePoint(...glyph.codePoints)}`);
  const position = run.positions[index];
  if (glyph.path) {
    pathData += glyph.path
      .scale(1, -1)
      .translate(x + position.xOffset, y + position.yOffset)
      .toSVG();
    x += position.xAdvance;
    y += position.yAdvance;
  }
});
console.log(pathData);
```
