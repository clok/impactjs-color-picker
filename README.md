# impact-color-picker

color-picker.js Plugin for ImpactJS that quickly generates gradient fades between multiple input colors.

Using this plugin (especially the genMultiHexarray) has greatly improved my content pipeline and overall game performance. The genMultiHexarray is fantastic for generating more complex color gradients like the Matlab Jet gradient which is very useful.

## DEMOS
[Simple canvas demo](http://www.clokwork.net/demos/color-picker/)

[PiSpace](http://www.clokwork.net/pispace/)

## How to Use
To use just include the plugin as 'plugins.color-picker' and instantiate a new ColorPicker object:
```JavaScript
var picker = new ColorPicker;
```

This will provide methods for generating custom colormaps and gradient fills.  There are generation functions and utility functions included:

### Generators
- genMultiHexArray
  - INPUTS: Array with any number of hex colors, number of steps
  - OUTPUT: Array with 'steps' entries between each sequential pair of colors in the input array. Each entry is a unique color.
```JavaScript
var lots_o_colors = picker.genMultiHexArray( [0xFF0000, 0x00FF00, 0x0000FF], 1000 );
```

- genHexArray
  - INPUTS: 2 hex colors as color1 and color2, number of steps
  - OUTPUT: Array with 'steps' entries between the two colors. Each entry is a unique color.
```JavaScript
var two_color_fade = picker.genHexArray( 0xFF8C00, 0x8400FF, 40 );
```

- pickHex
  - INPUTS: 2 hex colors as color1 and color2, ratio equivalent to a position between the two colors
  - OUTPUT: A single color representing that point in the gradient
```JavaScript
var single_color = picker.pickHex( 0xFF8C00, 0x8400FF, 0.63 );
```

###Utilities
- hexToRGBstr
  - INPUT: Single hex color
  - OUTPUT: "rgb( r, g, b )" string for the INPUT color
```JavaScript
var rgb_color = picker.hexToRGBstr( 0xFF8C00 );
```

- hexToRGBA
  - INPUT: Single hex color
  - OUTPUT: Array with [ r, g, b, a ], where a = 255
```JavaScript
var rgba_color_array = picker.hexToRGBA( 0xFF8C00 );
```

- frontPad
While str.length < 6, prepend 0's
  - INPUT: Single hex srting
  - OUTPUT: front padded hex value up to 6 characters

Cheers!