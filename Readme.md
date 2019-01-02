# Destyle.css

Opinionated [reset stylesheet](https://cssreset.com/what-is-a-css-reset/) that provides a clean styling slate for your project. All spacing (margin & padding) and font-sizing is removed and set to be inherited from its parent.

This approach avoids having to reset styles when creating different styled instances of the same element, it also contributes to the separation of presentation and semantics.

Like [normalize.css](https://github.com/necolas/normalize.css) just what needs reseting is reset to avoid bloat in the browser's style inspector.

## Installation

```shell
$ npm install --save destyle.css
```

Download: https://raw.githubusercontent.com/nicolas-cusan/destyle.css/master/destyle.css

## Usage

Include `destyle.css` in the `head` of your HTML file before your main stylesheet.

### Recommended

Add your base font and color styles to the `body` element in your stylesheet, all other elements will inherit the style from the body.

```css
/* app.css */

body {
  color: #333;
  font: 16px/1.4 'Helvetica Neue', sans-serif;
}
```

## Why?

Normalize.css just makes elements consistent between browsers and it does it well, but it does not remove the user agent's assumptions about how things have to look. Destyle.css removes these assumptions and makes the look of everything up to the stylesheet author.

As an example it facilitates styling headings differently depending on the context in with they are shown.

An `h1` might need to be bold & large in some context (like at the top of a text page) but might be small and inconspicuous in others (like a settings page in an app).

Creating two different styles for `h1` is made easy as only the styles you need to get the desired visual results have to be applied without the need to overwrite default styles while maintaining semantics.

How to create the styles is up to the author. It can be by creating classes, compose style using functional classes, styling inside a react component, etc. In any case the author always gets a clean slate for styling each element and it is up to him/her to reuse the styles or start from scratch for every instance.

## Rules & Caveats

- The box model is reset to `border-box` using the `*` selector
- `code`, `pre`, `kbd`, `samp` maintain a monospaced font-family
- `hr` is set to be a solid 1px line that inherits its color from its parent's text color
- Inline elements that carry style (`b`, `i`, `strong`, etc.) are not reset.
- `textarea` maintains its natural height.
- `select` is reset using `appearance: none` which is not cross-browser, be advised when styling custom selects. You can find a good guide [here](https://www.filamentgroup.com/lab/select-css.html)
- HTML5 Inputs like `range` and `color` are not reset.

## Credits

This project is heavily inspired by [normalize.css](https://github.com/necolas/normalize.css) and the original [reset](https://meyerweb.com/eric/tools/css/reset/) by Eric Meyer. The source of the test page is from [html5-test-page](https://github.com/cbracco/html5-test-page/pulls).
