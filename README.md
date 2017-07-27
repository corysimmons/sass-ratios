# sass-ratios
Sass function to generate ratio sizes.

Just grab the contents of [_sass-ratios.scss](_sass-ratios.scss) and `@import` it into your project somewhere.

https://alistapart.com/article/content-out-layout to learn more about why we should be using ratios in web-design.

## Demo

https://codepen.io/corysimmons/pen/XaJMXy

## Examples

```scss
// in.scss
.small-ratio {
  width: ratio(2, 1.5, 2);
}

.large-ratio {
  width: ratio(1, 1.5, 2);
}
```

```scss
// out.css
.small-ratio {
  width: calc(100% * 1.5/3.75);
}

.large-ratio {
  width: calc(100% * 2.25/3.75);
}
```

## Params/API

```scss
// @function ratio(
//   $index: 1,
//   $ratio: 1.618,
//   $count: 3,
//   $no-calc: null)
//
// Returns a single value from a list of ratio values.
//
// $index | 1-based index to get from the list of ratio fractions.
// $ratio | Whatever ratio you want to use as your base. Check out modularscale.com for fancy ideas.
// $count | The number of results you're working with, so if you want 4 sizes to work with, you'd set this to 4. It's used to generate the denominator for the returned fraction.
// $no-calc | By default these will return the fraction without a CSS calc() formula multiplyng the fraction by 100%. This is useful for widths/heights (most common usage), but you can disable this and just get the fraction by setting this to `true`.
```

## Globals

```scss
$global-ratio: 1.618 !default;
$global-count: 3 !default;
$global-no-calc: false !default;
```
