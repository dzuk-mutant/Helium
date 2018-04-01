# Thorium

Thorium is an experimental, small [Stylus]() framework designed for immersive, responsive interfaces that maximise the use of screen space, while cutting the bullshit as much as possible and keeping everything predictable *and* totally flexible.

Thorium is mostly just an array of prebuilt pieces and a variety of specific overrides to flatten out certain CSS behaviours. It also encourages a hearty use of Flexbox.

This doesn't do polyfills and doesn't support browsers from more than 5 years ago (as a general rule, some are much sooner). I try to aim for stuff that's at least 90% compatible in the present according to caniuse.com.

This is also a personal project and isn't necessarily structured in the best way or totally stable. So be careful about that.

<br/>

This has been used to make things like [Pineapple](https://github.com/dzuk-mutant/pineapple), [Mutant Standard's website](https://mutant.tech) and [instances.noct.zone](http://instances.noct.zone).

Check out the [documentation](docs/) if you're curious as to what's inside.

----

## Nice bits

- Lots of cute shortcuts to make prototyping interfaces using Flexbox much quicker and easier to understand.
- Shortcuts and fallbacks to make bidirectional design really simple.
- Tailored for full-screen web design as opposed to web design focused around a central column (although that's totally doable too).
- Made to reduce cognitive load when producing layouts by abstracting certain common positioning and sizing methods into single mixins/functions.

----

## How to use

import the `_thorium.styl` file in [`_thorium/`](_thorium):

eg. `@import '_thorium/_thorium.styl'`

----

## Licenses and Credits

Check out [the licenses folder](docs/licenses) folder for all licenses.

- Thanks to Amphetamine on Mastodon for the name idea. (The original name was far less savoury...)
