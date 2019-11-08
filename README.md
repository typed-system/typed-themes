# Typed Themes

Typed Themes is a collection of themes powered by [Typed System](https://github.com/typed-system/typed-system).

## Getting Started

A Theme usually consists of two schemes (or modes if you will), "Light" and "Dark".
Each scheme maybe has its own primary and secondary (accent) color. Some themes
maybe even have more than that, but let's assume the Apple case, where you only
have these two schemes and a primary and secondary
(or how they call it "accent" and "highlight") color.

## Themes

### Typed
---

[`@typed-themes/typed`](https://github.com/typed-system/typed-themes/tree/master/packages/typed)

Typed is the default theme as seen on [typed-system.com](https://typed-system.com)

## Theme Specification

A theme is defined by the following interface

```tsx
export type ObjectOrArray<T> = T[] | { [K: string]: T | ObjectOrArray<T> };

export type Scale = ObjectOrArray<number | string>;

export type LengthValue = string | 0 | number;

export type ResponsiveValue<T> = T | Array<T | null> | { [key: string]: T };

export interface Theme {
  /**
   * Name of the theme, e.g. "light"
   * */
  name: string
  /**
   * The spacing key is a specially-named scale intended for use with margin, padding, and other layout-related CSS properties.
   * A spacing scale can be defined as either a plain object or an array, but by convention an array is preferred.
   * This is an intentional constraint that makes it difficult to add "one-off" or "in-between" sizes that could lead
   * to unwanted and rippling affects to layout.
   *
   * Properties affeced by this key:
   * margin, margin-top, margin-right, margin-bottom, margin-left, padding, padding-top, padding-right,
   * padding-bottom, padding-left, grid-gap, grid-column-gap, grid-row-gap
   */
  spacing: ArrayOrObject<ResponsiveValue<LengthValue>>,
  // typography
  fontSizes,
  fonts,
  fontWeights,
  lineHeights,
  letterSpacings,
  // width, height, min-width, max-width, min-height, max-height
  sizes,
  // border
  borders,
  borderWidths,
  borderStyles,
  radii,
  // box-shadow, text-shadow
  shadows,
  // color, background-color, border-color
  colors,
  schemes,
  // z-space
  zIndices,
  elevations,
  // Responsiveness
  /**
   * Breakpoints are CSS lengths intended for use in media queries.
   * Commonly, the breakpoints scale is used to create mobile-first responsive media queries based on array values.
   *
   * Media Queries
   * For convenience and for use with other styling approaches, a mediaQueries scale derived from the breakpoints scale can be added to the theme object.
   *
   * breakpoints: [ '40em', '52em', '64em' ]
   *
   * mediaQueries: {
   *   small: `@media screen and (min-width: ${breakpoints[0]})`,
   *   medium: `@media screen and (min-width: ${breakpoints[1]})`,
   *   large: `@media screen and (min-width: ${breakpoints[2]})`,
   * }
   */
  breakpoints,
  mediaQueries,
  transitions,
  // RTL
  direction,
}
```

## Philosophy

TODO
