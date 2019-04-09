# Bidirectionality

Not all of the world's scripts read from left-to-right (LTR). Some of them read right-to-left (RTL), the biggest examples of which are Arabic and Hebrew.

Being a user of an RTL language breaks a lot of assumptions on interfaces LTR native language users can take for granted.

LTR/RTL doesn't just affect how text is read, but also how interfaces are read. The entire interface (with some exceptions that I'll get into) should be in direction with the script's direction. Icons for common functions can be reversed too, like back and forward.

Bidirectionality refers to designing interfaces and layouts that work properly in both reading directions.

<br/>

One of the things that makes Flexbox so great is that everything about it works bidirectionally by default, so if you use a lot of flexbox, you're most of the way there! Unfortunately, some aspects of CSS aren't there yet.

This is where these bidirectional mixins come in. These are simple shortcuts that just switch horizontal direction depending on the `dir` attribute (either `ltr` or `rtl`) of the parent.

There needs to be a `dir` attribute on the body element, or these will not work.

```
<body dir='ltr'>
	// STUFF
</body>
```

---

### What is 'start' and 'end'?

They refer to the position of something based on the *reading flow* of the script (whether it's LTR or RTL).

'Start' refers to the start of the reading flow - where text begins.

- In LTR that means 'start' is on the **left**.
- In RTL that means 'start' is on the **right**.

'End' refers to the end of the reading flow - where text ends. 

- In LTR that means 'end' is on the **right**.
- In RTL that means 'end' is on the **left**.


---


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