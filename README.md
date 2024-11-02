# Restart

_A modern CSS reset plus a few minimal styles – with dark mode compatibility._

`restart.css` version 1.2

Filesize: 4 KB (unminified)

Demo: https://simonpadbury.github.io/restart-css/
Changelog: https://github.com/SimonPadbury/restart-css/blob/main/CHANGELOG.md

***

The purpose of this tiny stylesheet is to provide a starting point for any web project — a reset/normalize _plus_ a little more styling for text, tables, forms and buttons. The styled HTML looks essentially the same on Chrome (and Chromium browsers, including Edge), Firefox, and Safari.

## What’s included

Out of the box, `restart.css` (4 KB) gives you:

1. Built-in automatic light/dark theme that follows the user’s operating system preference setting, using `html { color-scheme: light dark; }` (the demo toggle overrides this).
2. `:root` variables for:
    1. Three “web safe” font stacks (serif, sans, and mono);
    2. Basic typography settings (font size, line height, heading sizes);
    3. Colors for line details, form inputs, buttons, and code blocks. Now using the new CSS function `light-dark()` following ideas borrowed from Sara Joy’s [Come to the light-dark() Side](https://css-tricks.com/come-to-the-light-dark-side/). Read [more about this function on MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/light-dark).
 3. A tiny reset based on [Josh W Comeau’s custom CSS reset](https://www.joshwcomeau.com/css/custom-css-reset/) and [Andy Bell’s (more) modern CSS reset”](https://andy-bell.co.uk/a-more-modern-css-reset/).
 4. Accessability features: 
    1. a `:focus-visible` outline ring (for links, forms, and details `<summary>`) based on modern browser defaults, plus an outline-offset to improve readability;
    2. a `.visually-hidden` class.
 5. Minimal classless HTML styling for text, tables, and forms.
 6. “Responsive” control of image media (img, picture, canvas, video, svg) with `max-width: 100%`.
 7. The only CSS classes included are `.visually-hidden`, and `.button` (for when you want to style some links to look like buttons).

## Dark theme

There is no built-in dark theme, but there is what I’m calling dark mode _compatibility_. This includes:

1. Not setting most colors, so that you get the (user agent) browser defaults. These will change with the user’s operating system preference for light or dark mode.
2. Where necessary, styling a few elements with user agent controlled [system color names](https://developer.mozilla.org/en-US/docs/Web/CSS/system-color) (that are used by all the major browsers).
3. Setting a few base for line details (<hr> tag, table borders, form input borders), form inputs, an buttons using the new CSS function `light-dark()`.

That’s it. There are no `@media (prefers-color-scheme: ...) {}` in the stylesheet.

### How to control light/dark mode

You don’t need to do anything with `reset.css`. All you need to do is include the following meta tag in your HTML `<head>`:

```html
<meta name="color-scheme" content="dark light">
```

In this example, and in the demo `index.html`, `"dark"` is specified before `"light"` because my (the designer’s) preference for the webpage is that it have a dark theme. But it could have been the other way around.

With that meta tag in place, your browser then sets the _system colors_ in the browser according to what’s in the built in default stylesheet (`user-agent.css`). These are slightly different for different browsers, and they closely align with the operating system of the user’s device. In dark mode, text is generally white and the webpage (actually, canvas) background is a very dark gray, or black.

What you build on top of `restart.css` is, of course, up to you.

**Not included** in `restart.css`: an alternative way of enabling the user preference to choose the light or dark mode is to add `color-scheme: dark light;` to the document root, as follows:

```css
:root {
  color-scheme: dark light;
}
```

### The demo light/dark mode toggler

The demo `index.html` is has a simple JavaScript in its `<head>`. This JS is not necessary for `restart.css`, but is included for demonstration purposes. I copied it from Sara Joy’s [Come to the light-dark() Side](https://css-tricks.com/come-to-the-light-dark-side/).