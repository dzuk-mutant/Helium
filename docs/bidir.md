# Bidirectionality

Not all of the world's scripts read from left-to-right (LTR). Some of them read right-to-left (RTL), the biggest examples of which are Arabic and Hebrew.

Being a user of an RTL language breaks a lot of assumptions on interfaces LTR native language users can take for granted.

LTR/RTL doesn't just affect how text is read, but also how interfaces are read. The entire interface (with some exceptions that I'll get into) should be in direction with the script's direction. Icons for common functions can be reversed too, like back and forward.

Bidirectionality refers to designing interfaces and layouts that work properly in both reading directions.

<br/>

Flexbox really goes a long way to making interfaces that work in a bidirectional way by default, but some CSS styles don't have such features yet.

This is where these bidirectional mixins come in. These are simple shortcuts that just switch horizontal direction depending on the set `dir` (either `ltr` or `rtl`) of the `<html>` tag.

Your `<html>` needs a set `dir`, else these styles won't work.

---


### text-align: start/end
There are experimental values for `text-align` in CSS whereby you can align the text horizontally in a way that is relative to the reading flow, but unfortunately these aren't supported by all browsers.

With Thorium, you can use `text-align: start/end` and Thorium will automatically place a polyfill.

```
.blah
	text-align: end

.blah
	html[dir='ltr'] & { text-align: right }
	html[dir='rtl'] & { text-align: left }

```

---

### margin-start, margin-end, padding-start, padding-end
Create horizontal padding and margins that are relative to the reading flow.

```

.sigh
	margin-start: 420.69px

.sigh
	html[dir='ltr'] & { margin-left: 420.69px }
	html[dir='rtl'] & { margin-right: 420.69px }

```

---

### start/end

Create fixed/absolute positioning relative to the reading flow.

```

.jort
	end: 666px
	
	
.jort
	html[dir='ltr'] & { right: 666px }
	html[dir='rtl'] & { left: 666px }


```


---

### gutter-seq

gutter-seq also has bidirectional aspects that you can implement in your designs. Check [the documentation on gutters](gutter.md) for more information.