---
description: >-
  The `Path` object in Fontkit represents the outline of a glyph. You can use it
  to render the glyph on a canvas, SVG, or any other graphic surface.
---

# Path Object

{% hint style="info" %}
This documentation for [fontkit](https://github.com/foliojs/fontkit) is created and provided by the [Typogram](https://typogram.co/) team. It's a third-party documentation intended to delve deeper into the fontkit API. For the most accurate information, refer to [fontkit’s official documentation](https://github.com/foliojs/fontkit#readme).
{% endhint %}

## **Methods**:

### `path.rotate(angle)`

* **Description**: Rotates the path around the origin `(0, 0)`.
* **Parameters**:
  * `angle`: The rotation angle in radians.
* **Returns**: The modified `Path` object.
*   **Example**: Rotating a path by 45 degrees (converted to radians):

    ```javascript
    path.rotate(Math.PI / 4);
    ```

### `path.scale(scaleX, scaleY = scaleX)`

* **Description**: Scales the path by a factor in the x and y directions.
* **Parameters**:
  * `scaleX`: The scaling factor in the x-direction.
  * `scaleY`: (Optional) The scaling factor in the y-direction. If not provided, it defaults to the value of `scaleX`, resulting in uniform scaling.
* **Returns**: The modified `Path` object.
*   **Example**: Scaling a path by 2x in the x-direction and 0.5x in the y-direction:

    ```javascript
    path.scale(2, 0.5);
    ```

### `path.transform(m0, m1, m2, m3, m4, m5)`

* **Description**: Applies a 2x3 transformation matrix to the path. This can represent combinations of translations, rotations, scaling, and skewing.
* **Parameters**:
  * `m0`, `m1`, `m2`, `m3`, `m4`, `m5`: The elements of the 2x3 transformation matrix.
* **Returns**: The modified `Path` object.
*   **Example**: Applying a transformation matrix:

    ```javascript
    path.transform(1, 0, 0, 1, 10, 20); 
    // This example translates the path by 10 units in x and 20 units in y.
    ```

### `path.translate(x, y)`

* **Description**: Translates (moves) the path by a specified amount in the x and y directions.
* **Parameters**:
  * `x`: The translation amount in the x-direction.
  * `y`: The translation amount in the y-direction.
* **Returns**: The modified `Path` object.
*   **Example**: Translating a path by 10 units in x and 20 units in y:

    ```javascript
    path.translate(10, 20);
    ```

### `path.mapPoints(fn)`

* **Description**: Maps each point in the path to a new point by applying a given function. This is a general-purpose method that allows you to apply arbitrary transformations to each point in the path.
* **Parameters**:
  * `fn`: A function that takes a point as an argument (an object with `x` and `y` properties) and returns a new point (also an object with `x` and `y` properties).
* **Returns**: The modified `Path` object.
*   **Example**: Mapping points to apply a custom transformation:

    ```javascript
    path.mapPoints(point => ({
      x: point.x + 10,
      y: point.y - 5
    }));
    ```

### `path.moveTo(x, y)`

Moves the "pen" to a new location without drawing anything. This sets the starting point for a new sub-path.

### `path.lineTo(x, y)`

Draws a straight line from the current position to the specified (`x`, `y`) point.

### `path.curveTo(cp1x, cp1y, cp2x, cp2y, x, y)`

Draws a cubic Bezier curve from the current position to the specified (`x`, `y`) point using (`cp1x`, `cp1y`) as the control point for the start of the curve and (`cp2x`, `cp2y`) as the control point for the end of the curve.

### `path.qcurveTo(cpx, cpy, x, y)`

Draws a quadratic Bezier curve from the current position to the specified (`x`, `y`) point using (`cpx`, `cpy`) as the control point.

### `path.closePath()`

Closes the current sub-path by drawing a straight line back to its starting point. This is often used when defining closed shapes.

### `path.toSVG()`

Converts the path to an SVG path data string, which can be used to render the path using SVG.

### `path.toFunction()`

Converts the path to a JavaScript function with an API similar to the Canvas 2D context. This can be used for custom rendering.

## **Properties**:

### `path.commands`

An array of path commands. Each command is an object with a `type` property, which can be 'moveTo', 'lineTo', 'curveTo', 'qcurveTo', or 'closePath', and the corresponding x and y coordinates (or control points for curves).

### `path.bbox`

The bounding box of the path, which is the rectangle that encloses the path's outline. This object contains properties: `minX`, `minY`, `maxX`, and `maxY`.

### `path.cbox`

The control bounding box of the path, which is similar to the bounding box but includes Bezier control points.
