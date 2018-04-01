# Flex Shortcuts

Thorium features powerful shortcuts for implementing common usage patterns for flexbox.

Every shortcut is built on top of Thorium's flex mixins.

All usage patterns can be implemented in HTML (object-oriented style), or added to the code as mixins to be dynamically changed with things like @media queries.

---

## Structure
The flexbox container is whatever container you marked with the flex shortcut class. Items are anything inside the container (`> *`).

Every shortcut can have a specified direction. The only exception is `flexgrid()`, which needs to have a direction specified.

---

## Classes

### Linear

##### flexlinear()
A simple, linear, non-wrapping flex.

You can add an empty div with the class `.spacer-end` to push content to the other end of the container. It enables you to quickly create content that is oriented on both ends of the container space.

### 2D

##### flexwrap()
A simple, wrapping flex.

##### flexfit()
A simple, wrapping flex where all items stretch to fit remaining space along the main axis if there is surplus.


### Grids

##### flexblocks()
A wrapping flex where every item has the exact same length along the main axis.

Using it is like `display: inline-block`, but without any of it's frustrating quirks.


##### flexgrid()
A wrapping flex where every item has the exact same length along the main axis, and that length stretches evenly to fit inside the container.

You need to make extra items marked with a `dummy` class to make this effect work. They dummy items prevents any last trailing *visible* item to fill the last row/column, and lets the dummies take the fall instead.

You make enough dummy classes to make sure any non-dummy items in the container can't stretch longer than it's maximum possible width.

Requires a specified direction.

This is arguably better to use in many cases over `flexblocks` because in `flexgrid`, the items will always uniformly stretch to fit the container, which helps keep everything responsive and flexible.

### Positioning Objects

##### flexcenter()
A very simple shortcut for horizontally and vertically centering object(s) into a div. Has no inherent direction or direction options.