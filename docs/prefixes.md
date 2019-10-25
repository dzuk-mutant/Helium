# Prefixes
Helium supports a few properties and selectors in helping you deal with those pesky vendor prefixes.

---

## Single-line mixins
Remember that in Stylus, you don't have to write mixins like functions - you can just write them like a normal attribute and Stylus will act as if it's a mixin and do the appropriate prefixing for you.

If you do it this way, all this background compatibility work will be completely invisible.

#### user-select
When it is `none`, then it is prefixed to work across multiple browsers.

#### position
When it is `sticky`, it is prefixed to work across multiple browsers.

#### transform
Adds an extra prefix to work on Android 4.4 browser.

#### position
Adds an extra prefix to work on Android 4.4 browser.


---

## Block mixins

These are mixins that let you write one selector with block of code and have prefixes applied to that selector.

[Click here to look at Stylus' reference on block mixins.](http://stylus-lang.com/docs/mixins.html#block-mixins)

Example usage:

```
+placeholder()
	// block goes here

```

#### +placeholder()
So you can make `::placeholder` selectors.

#### +selection()
So you can make `::selection` selectors.
