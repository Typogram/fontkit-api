# Quick Start

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It’s a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

## Installation

Install via NPM:

```bash
npm install fontkit
```

## Load a font

{% tabs %}
{% tab title="ES6 (Browser)" %}
```python
import * as fontkit from 'fontkit';

const response = await fetch(url);
const arrayBuffer = await response.arrayBuffer();
const buf = new Uint8Array(arrayBuffer);
const font = fontkit.create(buf);
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
var fontkit = require('fontkit');

// open a font synchronously
var font = fontkit.openSync('font.ttf');
```
{% endtab %}
{% endtabs %}

## Layout a line of text

```javascript
const run = font.layout('Hello World!');
```

```javascript
const run = font.layout('Hello World!', {
  dlig: true,
  swsh: false,
  pcap: false
});
```

## Get pathData of a `GlyphRun`

```javascript
let pathData = '';
let x = 0;
let y = 0;
run.glyphs.forEach((glyph, index) => {
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
