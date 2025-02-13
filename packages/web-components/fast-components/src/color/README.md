# FAST Color Recipes

Color recipes are named colors who's value is algorithmically defined from a variety of inputs. `@microsoft/fast-components` relies on these recipes heavily to achieve expressive theming options while maintaining color accessability targets.

## Swatch
A Swatch is a representation of a color that has a `relativeLuminance` value and a method to convert the swatch to a color string. It is used by recipes to determine which colors to use for UI.

### SwatchRGB
A concrete implementation of `Swatch`, it is a swatch with red, green, and blue 64bit color channels .

**Example: Creating a SwatchRGB**
```ts
import { SwatchRGB } from "@microsoft/fast-components";

const red = SwatchRGB.create(1, 0, 0);
```

## Palette
A palette is a collection `Swatch` instances, ordered by relative luminance, and provides mechanisms to safely retrieve swatches by index and by target contrast ratios. It also contains a `source` color, which is the color from which the palette is 

### PaletteRGB
An implementation of `Palette` of `SwatchRGB` instances. 

```ts
// Create a PaletteRGB from a SwatchRGB 
const redPalette = PaletteRGB.from(red):

// Create a PaletteRGB from an object
const greenPalette = PaletteRGB.from({r: 0, g: 1, b: 0});

// Create a PaletteRGB from R, G, and B arguments
const bluePalette = PaletteRGB.create(0, 0, 1);
```