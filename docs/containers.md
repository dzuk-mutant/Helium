# Containers

This section is a work-in-progress.

## frame

This is designed to constrain all items with it's boundaries, so borders, padding, etc. do not increase the size of the visible element.

```

.frame {
	height: 100%
	width: 100%
	overflow: hidden // default behaviour
	display: flex

	> .container {
		flex: 1 1 auto // default behaviour
		align-self: stretch // default behaviour
	}
}

```