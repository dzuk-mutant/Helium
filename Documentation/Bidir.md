#Bidirectional

Flexbox really goes a long way to making interfaces that work bidirectionally by default, but some CSS styles don't have such features yet.

This is where bidirectional styles come in. These are simple shortcuts that just switch horizontal direction depending on the set `dir` (either `ltr` or `rtl`) of the `<html>` tag.

Your HTML needs a set direction, else these styles won't work.

---


### text-align-start, text-align-end
This is an interim replacement for `text-align: start` and `text-align: end`, which is a flow-relative solution to text-alignment (rather than the absolute values of `left` and `right`), which aren't compatible in enough browser yet to be really usable.

These mixins will just flip between the `left` and `right` values depending on the flow.

<br/>

`.text-align-start;` 

Makes the text align to the start of the flow.

<br/>

`.text-align-end;` 

Makes the text align to the end of the flow.

---

### margin-start, margin-end, padding-start, padding-end
Determine horizontal padding and margins based on the element's position relative to reading flow.

```

.margin-start(length);
.margin-end(length);
.padding-start(length);
.padding-end(length);

```

---

### gutter-seq-bidir, gutter-seq-this-bidir

Thorium's gutter is already bidirectional, but `gutter-seq` and `gutter-seq-this` are not, so there are bidirectional variants of these that work similarly to the margin mixins above.

Check out the gutter documentation for more information on these.
