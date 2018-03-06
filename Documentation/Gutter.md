#Gutters

Gutters are mixins that give you convenient ways to space out items.

##.gutter

The `.gutter` class adds 2D spacing to an array of objects, designed especially for flexbox items. This class ensures that all items within a container have even spacing in between them, but no spacing beyond on the edge of the container.

Like with flexbox, `.gutter` must be applied to a container to be applied to items.

Additionally (and unfortunately), there must either be a container outside that container with a `.gutter-clear` class (which is just `overflow: hidden;`) or a **frame** enclosing it. This is because to make the spacing work, Gutter applies positive margins to the items and a negative margin to the container, and that negative margin on the container will affect the flow of objects around it if it is not cancelled out. ¯\\\_(ツ)_/¯


###Implementation

There are both `.gutter` and `.gutter-pad` classes for different positioning scenarios.

As the name implies, `.gutter-pad` is a version where the items use padding rather than margin to create the gutter. However, both use negative margins for the container.

####Even Spacing

`.gutter(<margin>);`

`.gutter-pad(<margin>);`

Even spacing across both axes.

####Uneven Spacing

`.gutter(<margin-vertical>, <margin-horizontal>);`

`.gutter-pad(<margin-vertical>, <margin-horizontal>);`

Different spacing across each axis.

----

##.gutter-seq

(short for 'Sequential Gutter')

This is Thorium's mixin for the well-known first-child/last-child trick. This is generally only designed for one-dimensional spacing, but if you can think of a scenario for two-dimensional spacing, you can use it for that too.

This is much less flexible, but also doesn't require extra nested divs.


###Implementation

There is both `gutter-seq` for applying to all of a container's children, and `.gutter-seq-this` for applying to all of a particular class.

`.gutter-seq(<margin-vertical>, <margin-horizontal>, <seq-type>);`

`.gutter-seq(<margin-vertical>, <margin-horizontal>, <seq-type>);`

'seq-type' is which end(s) ('first', 'last', 'both') have the margin(s) removed.