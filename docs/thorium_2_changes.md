# Thorium 2 changes

This is a list of changes between this version of Thorium, and the original version.

Thorium 2 (this version) now uses [Stylus](http://stylus-lang.com) instead of Less. Expect to rewrite your styles because this syntax is different. But it shouldn't be too time-consuming.


## Changes

### Everything
A lot of files have been rearranged.


### New preprocessor

Thorium 2 (this version) now uses [Stylus](http://stylus-lang.com) instead of Less.

Some key differences to Less (ie. mostly unexpected stuff I learned when I ran into):

- Where we're going, we don't need curly braces or semi-colons. (You can have them if you really want to tho.)
- To negate a numerical variable's value, put a minus **with a space after it** and then the variable.
- Variables don't use `@`s before them. They don't necessarily need to have any special characters before them, but if you find that you really need it, use a `$` instead.
- You can't extend a class with another class by just entering that class. You have to use the `@extend` keyword. (very useful to know for `.spacer-end`~)

### Flexbox

There are no more flexbox mixins. I've decided they aren't needed anymore since UC Browser finally fully supports Flexbox. (And even if they did, thanks to Stylus' function notation, everything would be rewritten to pretend it doesn't exist anyway...)

**Reminder, don't use commas when using `flex`:**

ie.

```
flex: 1 1 auto

```

### Flex shortcuts

The keywords and classes `rows` and `columns` are no longer used. Use `row` and `column` instead as you would for standard flexbox CSS styling.

`flexgrid()` now supports `row-reverse` and `column-reverse`.


### Bidirectional mixins

Bidirectional mixins are more powerful now you can use them like normal CSS attributes.

```
// stylus

.thing
	text-align: end;

// css output

html[dir='ltr'] .thing {
  text-align: right;
}
html[dir='rtl'] .thing {
  text-align: left;
}

```

There are also new mixins! Check the [bidirectional documentation](bidir.md) for more info.

### gutter

##### gutter
`.gutter-clear` is gone. Manually use `overflow: none` on the container instead.

##### gutter-seq

`-bidir` variants of gutter-seq mixins have been merged into the standard variants.

Instead of defining both a vertical and horizontal, you specify the direction (`top`, `bottom`, `left`, `right`, `start` and `end`) and specify the distance and seq. You can repeat this function as many times as you need to if you need to apply it to more than one side.

### icons

`reduce()` has been renamed to `size-reduce()`.

### Misc
##### user-select: none
Now use `user-select: none`. The framework does the prefixing in the background.

##### position: sticky
Now use `position: sticky`. The framework does the prefixing in the background.


##### ::placeholder {}
`placeholder()` has been replaced with a [block mixin](http://stylus-lang.com/docs/mixins.html#block-mixins):

```
+placeholder()
	// block goes here

```

It's also now in `misc` instead of `forms` (which has been deleted).

##### Other misc mixins

All the other mixins from the v1 `misc.less` have been removed because they were unused or are now irrelevant.


### Graphics
- `transform` has been moved over to a [block mixin](http://stylus-lang.com/docs/mixins.html#block-mixins).
- `animation` has been moved over to a [block mixin](http://stylus-lang.com/docs/mixins.html#block-mixins).
- `keyframes` is being left behind because I'm not sure how to implement it anymore and I don't think it matters anymore.
- `transition` is no longer needed so it's being left behind.

### UI

Now merged into `overrides.styl`. There is no separate 'UI' segment anymore.

- `.btn-no-text` has been removed.
- `input.center` has been removed.
- `.input-c` has been removed.

### Display (@media screen queries)

Most display boundaries have shifted. 

There are also new labels for width boundary groups:

- `handset` (stays the same, still has 3 subsections)
- `medium` -> `portable` (with 3 subsections instead of 2)
- `wide` (stays the same, still has 2 subsections)

<br/>

- `handset-1`: 0px (stays the same)
- `handset-2`: 360px -> 350px
- `handset-3`: 400px (stays the same)
- `medium-1` -> `portable-1`: 520px -> 500px
- `medium-2` -> `portable-2`: 620px -> 650px
- `portable-3` (new): 850px
- `wide-1`: 900px -> 1050px
- `wide-2`: 1300px -> 1500px

Because of some strange quirk in Stylus, you access them via `sw` instead of just using teh names by themselves. eg:


```

@media sw.portable, sw.wide-1
	// blah

```

Plus, there are new height-based display buckets. Check [the new documentation on display](display.md) for more information.
