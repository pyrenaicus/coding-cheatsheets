# fluid typography

source: https://css-tricks.com/simplified-fluid-typography/

changing `font-size` as screen size changes

## using min() max()

```css
html {
  font-size: min(max(1rem, 4vw), 22px);
}
```

## using clamp()

```css
body {
  font-size: clamp(100%, 1rem + 2vw, 24px);
}
```

## using media queries and calc()

```css
html {
  font-size: 16px;
}
@media screen and (min-width: 320px) {
  html {
    font-size: calc(16px + 6 * ((100vw - 320px) / 680));
  }
}
@media screen and (min-width: 1000px) {
  html {
    font-size: 22px;
  }
}
```

`body { font-size: calc([minimum size] + ([maximum size] - [minimum size]) * ((100vw - [minimum viewport width]) / ([maximum viewport width] - [minimum viewport width]))); }`
