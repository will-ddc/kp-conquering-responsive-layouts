# 21 Day Course on Responsive Layouts by Kevin Powell

Quote: when you are fighting against a website its not because its not responsive its because we did something in our CSS that is making it fight

## Day 1 - Fixed Width vs % Notes

Default width for block elements is 100% viewport width of the parent element
fixed widths break native browser responsiveness

when adding fixed width to child elements you end up with overflow when the screen gets smaller than the fixed width.  this happens automatically by default css to make sure you don't lose the text or whatever is in the child element

you can use overflow: hidden on the parent element to hide any overflow in the child elements but then whatever is overflowing is just cut off

but a better way is to make sure the width in the child is set to a % instead of fixed height.  the width % is inhertied from the parent element, so if parent element is 80% of viewport width and child is set to 50%, it is 50% of the 80% and not the total viewport

you don't always need to set a width to child elements

This is a general rule. There are times when you want to use height, but for the most part, they cause more issues than they solve.

instead of setting a height use padding to get extra space in background of an element

its best to use em/rem than px since those are responsive

## Day 2 - No New Material

## Day 3 - adding max-width

max-width is used to limit wider screens from stretching too far

typically you don't want to set a min-width
