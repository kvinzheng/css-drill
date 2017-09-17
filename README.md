# HTML CSS NOTE

## How does html get render

In order to explain how floating works, you need to peek under the bonnet and look at how a web browser renders an HTML/CSS document.

Just as there are block-level and inline elements in HTML, there are block-level and inline boxes in CSS. By default, block-level elements generate block-level boxes and inline elements generate inline boxes. There will also be some generated boxes in addition to the ones generated by elements, for instance, for the next content of the document. Block boxes are normally laid out in the order the elements appear in the markup, from top to bottom. Block boxes cannot appear side-by-side unless we apply some CSS. Inline boxes are laid out horizontally. The direction property determines if they're laid out from left to right or from right to left(the default is left to right, if this is not specified)

This is known as the document flow: inline boxes from horizontally within their parent block boxes, and block boxes flow vertically. The boxes occur in the same order as elements in the HTML markup.

##  How does floating work?

The floated box is taken out of the document flow and shifted as far as possible to the left or to the right, depending on the specified floating direction. "As far as possible" means until the outer edge of the float touches the edge of the containing block. Thus, for float: left the box is moved to the left until the left margin of float touches the left edge of the parent.

However, there is a case that you need to be aware of. If there is already a box floated to the left when we float another box in the same direction, the second box will stop when it touches the first box. In another word, floats don't climb on top of one another. You can however still make this work by apply "position: relative;" . It will make it NOT static. Then you can apply index Z and margin: -100px to overlap them.

## Float

[source](https://developer.mozilla.org/en-US/docs/Web/CSS/float) - checkout float in mdn

The float CSS property specifies that an element should be placed along the left or right side of its container, allowing text and inline elements to wrap around it. The element is removed from the normal flow of the web page, though still remaining a part of the flow.

## How floated elements are positioned?
As mentioned above, when an element is floated, it is taken out of the normal flow of the document(though still remaining part of it). It is shifted to the left, or right, until it touches the edge of its containers box, or another floated element.

## z-index
z-index property will not apply to statically positioned elements. In order to use z-index the CSS must also include any position value other than static(ie relative, absolute, fixed). Just not static.

## the difference between inline, inline-block, block, none

**inline** : accept only margin-left and margin-right. The followings wouldn't work on inline: margin-top, margin-bottom, width, height

**block** : always start on a new line. It accept margin-top, right, bottom, left and width/height.

**inline-block** : It still act as a inline element and it wouldn't start on a new line. However, it now accepts margin-top, right, bottom, left and width/height.
