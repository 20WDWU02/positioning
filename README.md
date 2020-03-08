# Positioning Elements

The **position** property specifies where your elements are positioned on your webpage.  

There are 5 different position values
* static
* fixed
* relative
* absolute
* sticky

Along with these, you will be needing to use either the **top**, **bottom**, **left** or **right** property to adjust the positioning. This will only work if you give it a position other than static.

### Static

Static is the default position all elements have. This means they aren't positioned in any special way but are just positioned according to how you wrote them in your HTML. This will often be just stacking on top of each other.

### Fixed

Giving an element a fixed value will position it relative to the viewport/screen. This means it will be fixed in place as you scroll the page.

```css

#element {
    position: fixed;
    top: 0;
    left: 0;
}

```

This example will fix the element to the top left of the screen.

### Relative

Relative elements, by default, will behave the exact same as a static element. It is when you add in either of the extra positioning properties where it will change.  
When you add any of the extra properties, it will position it in relation to its original position. It will leave a blank space where the element originally was. It will also not effect or move other elements so often this will cause it to overlap other elements.

```css

#element {
    position: relative;
    top: 20px;
    left: 20px;
}

```
This example will move the element 20px from the top and left of its original positon.

### Absolute

This is the hardest position to understand.  
An element with absolute will position itself within its nearest relative parent.  
It will keep moving up the parent elements until it can find one with a position relative.  
If it can't find one, then it will use the body.

```css

#parentElement{
    position: relative;
}

#element{
  position: absolute;
  top: 50px;
  left: 50px;
}

```
This example will move the element 50px from the top and left of the parentElement.  

**Note** People often forget to put absolute elements inside of a relative container so if you are wanting to use absolute, you need to have it within a container.

### Sticky

Sticky elements toggle its positioning between fixed and relative depending on where you are on the page.
Until you get to the position you set with your top, bottom, left or right, it will be relative. But once it meets those values, it will be fixed.

```css

#element{
  position: -webkit-sticky; /* Safari */
  position: sticky;
  top: 0;
}

```

This example element will be relative until it reaches the top of the screen (top:0) where it will then become fixed.

**Note** IE/Edge 15 and earlier versions do not support sticky position.  
**Note** If you want sticky to work on Safari you need to include the -webkit-sticky value as well.  
