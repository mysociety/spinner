# mySociety spinner

A customisable CSS-only animated spinner.

![example](demo/screengrab.gif)

## How to use this

Include `spinner.scss` in your project’s Sass pipeline, eg:

```scss
@include "spinner";
```

The variables at the top of `spinner.scss` are declared as [defaults](https://sass-lang.com/documentation/variables#default-values) so if you want to customise the spinner, you don’t need to edit those variables in-place, you can override them elsewhere in your Sass files, before `spinner.scss` is imported, eg:

```scss
$mysoc-spinner-diameter: 3em;
$mysoc-spinner-thickness: 0.25em;
$mysoc-spinner-color: inherit;

@include "spinner";
```

Since the spinner’s colour is based on the `.mysoc-spinner` element’s `color` style, you can also override it in the HTML or via JavaScript, like so:

```html
<!-- HTML inline style -->
<div class="mysoc-spinner" style="color: pink"></div>

<!-- or via JavaScript -->
<script>
document.querySelector('.mysoc-spinner').style.color = "pink";
</script>
```

## Accessibility

The demo at `demo/index.html` includes `role="status"` and a visually hidden text label for the spinner, to improve accessibility. There are cases when this default markup might not be suitable – remind yourself of [when and how to use the ARIA `status` role](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_status_role).

You should also consider the contrast level between the `$mysoc-spinner-color` and its background. [WCAG 2.1 requires a contrast ratio of 3:1](https://www.w3.org/TR/WCAG21/#non-text-contrast) for Level AA compliance.

## Browser support

This spinner relies on CSS Transforms and CSS Animations. It includes `-webkit-transform` and `-webkit-animation` fallbacks. That means it works on:

| IE  | Edge | Firefox | Chrome | Safari | iOS Safari |
|:---:|:----:|:-------:|:------:|:------:|:----------:|
| 10+ |  All |   16+   |   4+   |   4+   |     6+     |

If you don’t care about support for old Webkit browsers, you can set the `$mysoc-spinner-webkit-compatibility` variable to `false`, or simply remove the relevant `@if` blocks entirely from `spinner.scss`, resulting in support for only modern browsers:

| IE  | Edge | Firefox | Chrome | Safari | iOS Safari |
|:---:|:----:|:-------:|:------:|:------:|:----------:|
| 10+ |  All |   16+   |   43+  |   9+   |     9+     |

## How to run the demo locally

You will need the [Sass command line executable](https://sass-lang.com/install) installed. Then, run:

    make watch

You can now open `demo/index.html` in your web browser.
