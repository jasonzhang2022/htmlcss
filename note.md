**stacking context**

[official description](http://www.w3.org/TR/CSS2/zindex.html)

A and B are siblings

A has children  A1, A2,

If A, A1, A2, B are in the same stacking context, the deep element(children of A: A1, A2) will overlay on top of shallow elements B.

**Float**

[basic ](http://css.maxdesign.com.au/floatutorial/introduction.htm)

content in Element after floating element will wrap around float element.  But its dimension is drawn out as if the floated element does not exist. This could be that we only can have box model, we could not have polygon model. While content will wrap around a floated element, border, background image and background color will extend underneath.

**counter vs counters**

counter(identifier) is used to generate content for one-level counting. counters(identifier, separator) is used to generate content for multiple-level counting.

**miscallenous**
border-collapse, border-spacing

clip

cursor

empty-cells:hide/show

overflow: auto, scroll, hidden,visible

q {
    quotes: "«" "»" "‹" "›";
}

resize: auto|both|horizontal|vertical

pre {tab-size: 16;}
