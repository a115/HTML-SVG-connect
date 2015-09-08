# HTML SVG connect

jQuery plugin for drawing paths between arbitrary HTML elements (with SVG).

---

## Usage

First, load jQuery and the plugin:

```html
<script src="jquery.min.js" type="text/javascript"></script>
<script src="jquery.html-svg-connect.js" type="text/javascript"></script>
```

Attach it to your container element on DOM ready, and define your paths as an array. Each path is an object with the start and end elements defined as CSS selector **ID**s:

**(The elements don't have to be different; you can specify that any *one* element connects with any number of different elements.)**
```html
<script type="text/javascript">
    jQuery(document).ready(function($) {
      $("#svgContainer").HTMLSVGconnect({
        paths: [
          { start: "#red", end: "#aqua" },
          { start: "#purple", end: "#green" }
        ]
      });
    });
</script>
```

This will draw an SVG graphic with two pipes between the respective elements, and recalculate them as the window re-sizes.

### Options

These are defined as properties at the same level as the *paths* property.

| Name          | Type  | Description  | Default |
| ------------- | ----- | :------------ | ------- |
| stroke | string | Path colour | #000000 |
| strokeWidth | integer | Path thickness (px) | 10 |
| orientation | string | Whether the path begins/ends from the side of the element or from the top/bottom. Options: [horizontal &#124; vertical &#124; auto] | auto |

**The global options can also be overridden on a per path basis:**

```js
{
  stroke: "00FF00",
  strokeWidth: 12,
  paths: [
    { start: "#red", end: "#aqua", stroke: "#FF0000", strokeWidth: 8 },
    { start: "#purple", end: "#green", orientation: "vertical" }
  ]
}
``` 

## Author

Owain Lewis / A115

Based on work by [alojzije](https://github.com/alojzije): [connectHTMLelements_SVG.png](https://gist.github.com/alojzije/11127839)

## Other

[MIT License](http://www.opensource.org/licenses/mit-license.php)
