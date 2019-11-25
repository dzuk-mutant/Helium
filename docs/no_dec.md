# No Decoration

These are a series of classes to extend when you want to clear default styles for various semantic HTML tags that have very specific/strong default style behaviour.

---

## `a.no-dec`
Removes default link colours and underlines.

```
menu
    a.home
        @extends a.no-dec
        // applies no-dec to a.home.

```

## `ul.no-dec`
Removes default spacing and list decoration for unordered lists and their direct `li` children.

```
menu
    ul.sections
        @extends ul.no-dec
        // applies to ul.sections itself and it's direct li children.

```
