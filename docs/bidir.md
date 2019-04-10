# Bidirectionality

One of the things that makes Flexbox so great is that everything about it works bidirectionally by default, so if you use a lot of flexbox, you're most of the way there! Unfortunately, some aspects of CSS aren't there yet.

This is where these bidirectional mixins come in. These are simple shortcuts that just switch horizontal direction depending on the `dir` attribute (either `ltr` or `rtl`) of a specified parent HTML element.

---

## How to use

You need to have a `dir` attribute on a parent element to the elements you're going to use the mixin on. By default, it's set to `<body>`.

```
<body dir='ltr'>
	// STUFF
</body>
```

---

### Overriding the default dir location

Insert this code snippet towards the beginning of your imports, with the HTML element of your choice, (after Helium and your plugins) to change where the parent dir location is without having to manually edit Helium:

```

dir-ltr()
	<override element>[dir='ltr'] &
		{block}


dir-rtl()
	<override element>[dir='rtl'] &
		{block}

```


---


## Mixins

### text-align: start/end
There are experimental values for `text-align` in CSS whereby you can align the text horizontally in a way that is relative to the reading flow, but unfortunately these aren't supported by all browsers.

With Helium, you can use `text-align: start/end` and Helium will automatically place a polyfill.

```
// Stylus

.blah
	text-align: end


// What the mixin does

.blah
	body[dir='ltr'] &
		text-align: right

	body[dir='rtl'] &
		text-align: left
		


// Generated CSS

body[dir='ltr'] .blah { 
	text-align: right
}

body[dir='rtl'] .blah {
	text-align: left
}

```

---

### margin-start, margin-end, padding-start, padding-end
Create horizontal padding and margins that are relative to the reading flow.

```

// Stylus

.sigh
	margin-start: 420.69px


// What the mixin does

.sigh
	body[dir='ltr'] &
		margin-left: 420.69px

	body[dir='rtl'] &
		margin-right: 420.69px
		
		
// Generated CSS

body[dir='ltr'] .sigh {
	margin-left: 420.69px
}

body[dir='rtl'] .sigh {
	margin-right: 420.69px
}

```

---

### start/end

Create fixed/absolute positioning relative to the reading flow.

```

// Stylus

.jort
	end: 666px
	
	
// What the mixin does

. jort
	body[dir='ltr'] &
		right: 666px
		
	body[dir='rtl'] &
		left: 666px
		
	
	
// Generated CSS

body[dir='ltr'] .jort { 
	right: 666px 
}
body[dir='rtl'] .jort { 
	left: 666px 
}


```


---

### gutter-seq

`gutter-seq` can also be used bidirectionally. Check body[the documentation on gutters](gutter.md#gutter-seq) for more information.