**stacking context**

[official description](http://www.w3.org/TR/CSS2/zindex.html)

A and B are siblings

A has children  A1, A2,

If A, A1, A2, B are in the same stacking context, the deep element(children of A: A1, A2) will overlay on top of shallow elements B.

**Float**

[basic ](http://css.maxdesign.com.au/floatutorial/introduction.htm)

Display for float is automatically block. See the float.html under this directory for a demo.

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

**Negative Margin**
[guide](http://www.smashingmagazine.com/2009/07/the-definitive-guide-to-using-negative-margins/)

**Use percentage for margin and border **
[guide] (http://mattsnider.com/css-using-percent-for-margin-and-padding/)

The percentage for margin and border is the percentage of the **width** of the containing element. It is relative to **width not height** event for margin-top, margin-bottom, padding-top and padding-bottom.

You can not use percentage for border.

You can use percentage for border-radius. It is relative to **target element not containing element**

Percentage can be used for transform. It is relative to **target element not containing element **

When use percent for position attribute (top and left), top is the percentage of the height of containing element and left is the percentage of width of containing element.
