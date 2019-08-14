# mySociety spinner

A customisable CSS-only animated spinner.

![example](demo/screengrab.gif)

## How to use this

Include `spinner.scss` in your project’s Sass pipeline.

The variables at the top of `spinner.scss` are declared as [defaults](https://sass-lang.com/documentation/variables#default-values) so if you want to customise the spinner, you don’t need to edit those variables in-place, you can override them elsewhere in your Sass files, before `spinner.scss` is imported.

Since the spinner’s colour is based on the `.mysoc-spinner` element’s `color` style, you can also override it in the HTML or via JavaScript, like so:

    <!-- HTML inline style -->
    <div class="mysoc-spinner" style="color: pink"></div>

    <!-- or via JavaScript -->
    <script>
    document.querySelector('.mysoc-spinner').style.color = "pink";
    </script>

## Browser support

This spinner relies on CSS Transforms and CSS Animations. It includes `-webkit-transform` and `-webkit-animation` fallbacks. That means it works on:

| IE  | Edge | Firefox | Chrome | Safari | iOS Safari |
|:---:|:----:|:-------:|:------:|:------:|:----------:|
| 10+ |  All |   16+   |   4+   |   4+   |     6+     |

If you don’t care about support for old Webkit browsers, you can set the `$mysoc-spinner-webkit-compatibility` variable to `false`, or simply remove the relevant `@if` blocks entirely from `spinner.scss`, resulting in support for only modern browsers:

| IE  | Edge | Firefox | Chrome | Safari | iOS Safari |
|:---:|:----:|:-------:|:------:|:------:|:----------:|
| 10+ |  All |   16+   |   43+  |   9+   |     9+     |

## How to run this locally

You will need the [Sass command line executable](https://sass-lang.com/install) installed. Then, run:

    make watch

You can now open `demo/index.html` in your web browser.
