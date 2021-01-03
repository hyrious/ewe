## SVG, Canvas(2d), WebGL?

There are several ways to do visualization on the web.
~~DOM~~, SVG, Canvas(2d) and WebGL, which to use?

### SVG: Few Vectors

If we need vectors sharp and clear even when being zoomed in,
use SVG. But everything beyond vectors is maybe hard to accomplish.
BTW, there is `<foreignObject>` which can be used to display texts and
other non-svg assets. SVG is always a good choice for few vectors.

### Canvas: More Vectors and... Sprites!

If we want to "draw by hand", canvas(2d) is taken into consideration.
Here the `2d` means `canvas.getContext('2d')`. You can achieve almost
everything that SVG can do in a 2d canvas context. [OffscreenCanvas][]
and other optimization methods can be used to make it look better.

### WebGL: Tons of Vectors and... Shaders!

I'm talking about `canvas.getContext('webgl2')`. Finally we could
write shaders and control the drawing in a lower way without
seeing program crashing :/ But this also brings new problems like
copying the webgl2 canvas to a 2d canvas.

### Summary

[EWE](https://github.com/hyrious/ewe) is targeting the latest stable
browsers (chrome & firefox) with the help of modern web API.
It may use 2d-canvas and webgl2 hybrid method to do the graphics.

[OffscreenCanvas]: https://developer.mozilla.org/en-US/docs/Web/API/OffscreenCanvas
