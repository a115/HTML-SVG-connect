# HTML SVG connect
[![npm](https://img.shields.io/npm/v/html-svg-connect.svg?maxAge=2592000)](https://www.npmjs.com/package/html-svg-connect)

jQuery plugin for drawing responsive paths between arbitrary HTML elements (with SVG).

View demo at http://a115.github.io/HTML-SVG-connect/

---

## Install
Load jQuery and the plugin:
```html
<script src="jquery.min.js" type="text/javascript"></script>
<script src="jquery.html-svg-connect.js" type="text/javascript"></script>
```
or install with npm:
```
npm install html-svg-connect
```

## Usage

Attach it to your container element on DOM ready, and define your paths as an array. Each path is an object with the start and end elements defined as CSS selector **ID**s:

**(The elements don't have to be different; you can specify that any *one* element connects with any number of different elements.)**
```html
<script type="text/javascript">
    jQuery(document).ready(function($) {
      $("#svgContainer").HTMLSVGconnect({
        paths: [
          { start: "#red", end: "#aqua", text: "hello" },
          { start: "#purple", end: "#green", text: "world" }
        ]
      });
    });
</script>
```

This will draw an SVG graphic with two pipes with text written along each between the respective elements, and recalculate them as the window re-sizes.

Paths can also be added on-demand after loading (e.g., after an AJAX call), by calling **addPaths** with an array of path objects to add (this array has the same options available as when initialising paths).

```javascript
var newPaths = [
  { start: "#red", end: "#green", text: "foo" }, 
  { start: "#aqua", end: "#green", text: "bar" }
 ];
$("#svgContainer").HTMLSVGconnect("addPaths", newPaths);
```

### Options

These are defined as properties at the same level as the *paths* property.

| Name          | Type  | Description  | Default |
| ------------- | ----- | :------------ | ------- |
| stroke | string | Path colour | #000000 |
| strokeWidth | integer | Path thickness (px) | 10 |
| orientation | string | Whether the path begins/ends from the side of the element or from the top/bottom. Options: [horizontal &#124; vertical &#124; auto] | auto |
| offset | integer | Number of pixels added to the path before the first curve. | 0 |
| class | string | Path class (css) name. | empty |
| text | string | Text to be written along the path. | empty |

**The global options can also be overridden on a per path basis:**

```js
{
  stroke: "#00FF00",
  strokeWidth: 12,
  class: "",
  paths: [
    { start: "#red", end: "#aqua", stroke: "#FF0000", strokeWidth: 8 },
    { start: "#purple", end: "#green", orientation: "vertical", offset: 20, class: "dashed-blue" }
  ]
}
```

## Author

Owain Lewis / A115

Based on work by [alojzije](https://github.com/alojzije): [connectHTMLelements_SVG.png](https://gist.github.com/alojzije/11127839)

## Other

[MIT License](http://www.opensource.org/licenses/mit-license.php)
