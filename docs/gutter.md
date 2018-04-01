# Gutters

Gutters are mixins that give you convenient ways to space out items.

## gutter()

The `gutter()` mixin adds 2D spacing to an array of objects, designed especially for flexbox items. This class ensures that all items within a container have even spacing in between them, but no spacing on the edges of the container.



### Implementation

`gutter()` must be applied to the container.

```
.container
	gutter(10px 20px)
	
.container
	margin-top: - 10px
	margin-left: - 20px

	& > *
		margin-top: 10px
		margin-left: 20px


```

There are both `gutter()` and `gutter-pad()` classes for different positioning scenarios.

- `gutter()` uses margins to space the items.
- `gutter-pad()` uses padding to space the items.
- Both still apply negative margins to the container.


There must be a container outside the container with a `overflow: hidden`. This is because to make the spacing work, `gutter()` applies positive margins to the items and a negative margin to the container, and that negative margin on the container will affect the flow of objects around it if it is not cancelled out by something surrounding it.

```
<div style='overflow: hidden`>
	<div class='this-has-a-gutter-mixin'>
		<div>...</div>
		<div>...</div>
		<div>...</div>
		<div>...</div>
	</div>
</div>

```

You can also choose to space each axis differently, or space them both in the same way:

#### Even spacing across both axes

`gutter(val)`

`gutter-pad(val)`


#### Different spacing on each axis

`gutter(vertical, horizontal)`

`gutter-pad(vertical, horizontal)`


#### Bidirectionality

Because what `gutter()` does applies equally in both horizontal directions, it doesn't matter if it applies a left margin, so you can use it in a bidirectional design context without any issues.

----

## gutter-seq()

(short for 'Sequential Gutter')

This is Thorium's mixin for the well-known first-child/last-child trick. This is generally only designed for one-dimensional spacing, but if you can think of a scenario for two-dimensional spacing, you can use it for that too.

This is much less flexible, but also doesn't require extra nested divs.

You use this on the container and it is applied to all children.


### Implementation
There are two variants of gutter-seq:

- `gutter-seq()` is applied to a container to affect all it's children.
- `gutter-seq-this()` is applied to the items themselves.

### Values

`gutter-seq(direction, length, seq)`

`gutter-seq-this(direction, length, seq)`


<br/>

`direction` can be:

- `top`
- `bottom`
- `left`
- `right`
- `start` (start of reading flow)
- `end` (end of reading flow)

`length` is how much in that direction you want the spacing to be.


`seq` is where you decide what which object at what end has their margins cancelled out: 


- `first`
- `last`
- `both`
- `none`


<br/>

Using `start` or `end` is highly recommended and necessary if you want to make sure your spacing works in a bidirectional design context.

