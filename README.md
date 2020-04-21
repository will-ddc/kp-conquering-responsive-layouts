# 21 Day Course on Responsive Layouts by Kevin Powell

Quote: when you are fighting against a website its not because its not responsive its because we did something in our CSS that is making it fight

## Day 1 - Fixed Width vs % Notes | Challenge #1

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

## Day 3 - adding max-width | Challenge #2

max-width is used to limit wider screens from stretching too far

typically you don't want to set a min-width

## Day 4 - No New Material - Video on using VW and VH

https://www.youtube.com/watch?v=IWFqGsXxJ1E

## Day 5 - Challenge #3

create copy of the design spec pdf included

## Day 6 - Review Of First Week

Don't use em/rem for setting font-size
The Tale of width and max-width: https://css-tricks.com/tale-width-max-width/

## Day 7 - Solution to Challenge 3

Emmet documentation - https://docs.emmet.io/

BEM - https://youtu.be/SLjHSVwXYq4

box-sizing: border-box - https://youtu.be/WlGQdgy-M6w

## Day 8 - Flexbox Basics

when adding display: flex you are turning that element into a flex container, all of its children elements become flex items

the default flex-direction is row.  flex-direction: column; turns that default into columns

flex items always try and shrink down to smallest possible size

flex items will fit in one row even if it needs to break out and cause sidescrolling

to ensure flex items are same size even if content size is different add width: 100% to the flex items or whatever width you are going for

beware that only children of the flex parent become flex items, the grandchildren, etc.  do not become part of the flex container/flex item relationship

there are two ways to create space between flex items:
	1) gap - you would just add gap: 50px to the flex container and each flex item would have a gap of 50px between them without affecting content layout.  ** this is only supported by firefox at the moment though, keep an eye on caniuse.com
	2) using the + css selector - so .col + .col will select all the .col in a .row flex container but the first one and then add margin-left with the desired gap


## Day 9 - Deeper Dive Into Flexbox

as
