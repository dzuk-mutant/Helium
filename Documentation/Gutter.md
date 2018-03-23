# Gutters

Gutters are mixins that give you convenient ways to space out items.

## .gutter

The `.gutter` class adds 2D spacing to an array of objects, designed especially for flexbox items. This class ensures that all items within a container have even spacing in between them, but no spacing on the edges of the container.

`.gutter` must be applied to a container to be applied to items.

Additionally (and unfortunately), there must either be a container outside that container with a `.gutter-clear` class (which is just `overflow: hidden;`) or a **frame** enclosing it. This is because to make the spacing work, Gutter applies positive margins to the items and a negative margin to the container, and that negative margin on the container will affect the flow of objects around it if it is not cancelled out. ¯\\\_(ツ)_/¯


### Implementation

There are both `.gutter` and `.gutter-pad` classes for different positioning scenarios.

As the name implies, `.gutter-pad` is a version where the items use padding rather than margin to create the gutter. However, both use negative margins for the container.

#### Even spacing across both axes

`.gutter(@margin);`

`.gutter-pad(@margin);`

Even spacing across both axes.

#### Different spacing on each axis

`.gutter(@margin-vertical, @margin-horizontal);`

`.gutter-pad(@margin-vertical, @margin-horizontal);`

Different spacing across each axis.

----

## .gutter-seq

(short for 'Sequential Gutter')

This is Thorium's mixin for the well-known first-child/last-child trick. This is generally only designed for one-dimensional spacing, but if you can think of a scenario for two-dimensional spacing, you can use it for that too.

This is much less flexible, but also doesn't require extra nested divs.

You use this on the container and it is applied to all children.


### Implementation

There is both `gutter-seq` for applying to all of a container's children, and `.gutter-seq-this` for applying to all of a particular class.

`.gutter-seq(@margin-vertical, @margin-horizontal, @seq);`

`.gutter-seq(@margin-vertical, @margin-horizontal, @seq);`

`@seq-type` is which object at what end ('first', 'last', 'both') have the margin(s) removed.


----

## .gutter-seq-this

Apply a sequential gutter to the elements directly instead of the parent that contains them.

----

## .gutter-seq-bidir, .gutter-seq-this-bidir

These are variants of `gutter-seq` and `gutter-seq-this` for bidirectional interfaces and layouts. Instead of declaring absolute margins, you declare ones that are relative to the reading direction.

Because bidirectionality only applies to horizontal metrics, these mixins only work horizontally.

(Check out the documentation on Bidirectionality for more information on that kind of stuff)

`.gutter-seq-bidir(@dir, @distance, @seq)`

`.gutter-seq-this-bidir(@dir, @distance, @seq)`

- `@dir` is either `start` or `end`. 
- `@distance` is the measurement of how much you want that spacing to be (ie. `9px`, `2em`, etc.)
- `@seq` is the same as the previous mixins - which object at what end (`first`, `last`, `both`) have the margin(s) removed. 