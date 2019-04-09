# Helium

Helium is an experimental, small [Stylus]() framework designed for immersive, responsive interfaces that maximise the use of screen space, cutting frustrating CSS tendencies as much as by enforcing that everything remains predictable *and* totally flexible.

Helium is mostly just an array of prebuilt pieces and a variety of specific overrides to flatten out certain CSS behaviours. It also encourages a hearty use of Flexbox.

To keep compiled CSS sizes down and because flexbox is a given, Helium intentionally doesn't support browsers from more than 5 years ago (as a general rule, some are much sooner). If you want something more backwards compatible, looking for another CSS framework would probably be better for you.

This is also a personal project and isn't necessarily structured in the best way or totally stable. So be careful about that.

----

## Helium in action

- [Pineapple](https://github.com/dzuk-mutant/pineapple)
- [Mutant Standard's website](https://mutant.tech)
- [My personal website](https://noct.zone)
- [instances.noct.zone](http://instances.noct.zone).


----

## Nice bits

- Lots of cute shortcuts to make prototyping interfaces using Flexbox much quicker and easier to understand.
- Shortcuts and fallbacks to make bidirectional design really simple.
- Tailored for full-screen web design as opposed to web design focused around a central column (although that's totally doable too).
- Made to reduce cognitive load when producing layouts by abstracting certain common positioning and sizing methods into single mixins/functions.

----

## How to use

Copy and paste the helium folder where you need it and then just import it in your styles (as one of the first imports). Then you can reference all of it's features in your style sheets!

```
@import '/helium'

```
----

## Docs

I keep Helium pretty well documented!

[You can read all of the documentation here.](docs/docs.md)


----

## Licenses and Credits

[Helium is licensed under the MIT license](license.txt).
