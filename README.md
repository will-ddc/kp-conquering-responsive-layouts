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

when adding images or multiple columns into a flex container each column stretches to match the column with the largest content so images can be stretched or squashed depending on text columns.  one way to fix this is to add align-items: flex-start to the flex container so that each flex item starts at the top left of the flex container, but if you want to keep you flex container css as small as possible you can wrap the image in its own div tag and you want need the align-items added into your css.  if you are trying to keep your html markup down as much as possible add a class to the image tag and use align-self: flex-start on that class.  

align-items is used on flex-containers to effect on all flex items where as align-self is for individual flex items

because flex items always try and take up the smallest amount of space possible you may want them to take up more or less room,  use width to accomplish this.  you could set a text container to width:60% and the image to width: 30% and that way they will take up that much space respectivley.  now you could use margin-left or -right to push items away from each other to create white space but if you change the width then you need to change the margin as well.  an easier method would be to use justify-content.

justify-content is applied on the flex container and tells the flex items to space out or justify the space between them

default is flex-start

to make images fully responsive always add max-width: 100% to the img tag in css


## Day 10 - No New Material

https://www.youtube.com/playlist?list=PL4-IK0AVhVjMSb9c06AjRlTpvxL3otpUd - flexbox videos by Kevin Powell


## Day 11 - Using Flexbox for Navigation

no new info, just challenge to create nav bar layout using flexbox

## Day 12 - Getting Fancy with Navigation

when creating navigation with flexbox you end up nexting multiple flex containers within each other which can start to make getting the exact layout your looking for difficult.  you can set the width to 100% or whatever to try and force it to take up all required space but that doesn't always work.  

to align items vertically when you start adding logos and other things that are bigger than your nav links you use align-items to align the flex items in the container to the start end or center

when you get enough flex containers nested you need to become aware of and use flex-grow and flex-shrink properties on the containers

flex-grow is set to 0 by default and is what makes flex items want to stay as small as possible in their flex container

flex-shrink is is set to 1 by default and is what makes flex items shrink


if you want your nav to have the logo on the left, main links centered and the login links to the right you would need to added extra classes and use margin: 0 auto;


## Day 13/14 - No New Content


## Day 15 - Intro into media queries

most common media query used is min-width or max-width.
min-width means the minimun width declared or bigger
max-width means the max width declared or smaller

you can combine min and max width as well

examples:

* below is for screens 600px and bigger, the background changes to blue.  with other css this would be considered mobile first as the media query targets bigger screens

@media (min-width: 600px) {
    .body {
      background-color: blue;
    }
}

* below is for screens 600px or smaller, the background changes to red.  with other css this would be considered a desktop first approach as the media query targets smaller screens

@media (max-width: 600px) {
    .body {
      background-color: red;
    }
}

you should try and use a mobile first approach as it normally takes more changes to take  a desktop layout and turn it mobile as opposed from taking a mobile layout to desktop

you always want your media query below all other css otherwise it may not always override how you want it to


## Day 16 - What Break Points To Use

look at media query breakpoints as the point at which your layout breaks

try and create as few breakpoints as possible, but you may need several.  don't try and target specific devices but a general px of most devices

you'll find several breakpoints that you basically always use, 600-700px and 900-960px are two common ones, then for laptop/desktop screens 1200px and for large laptop/desktop 1800px


## Day 17 - viewport meta tag

this important meta tag is very important, it tells the page what the max-width of the device accessing your site is so the correct media query is being used.  make sure to include this tag on any html page

** Firefox web browser does a great job of compensating for this if the tag is forgotten but other browsers not so much **


## Day 18 - Day 12 Challenge Solution w/ Mobile First Approach

Learn About CSS custom properties - https://youtu.be/PHO6TBq_auI

Learn About CSS height/width measurements - https://youtu.be/IWFqGsXxJ1E

when coding for mobile first while your css is based on this approach write your HTML based on the large screen layout so you have better control on basic layout

when using larger font-sizes make sure to be setting line-height: 1 or around there or the spacing can get out of hand

generally the smallest devices are 320px wide

the advantage to doing a mobile first css approach is generally your css doesn't need fancy layout just the fonts, colors, and some spacing to make it look good on mobile devices, except your navigation bar may need some extra layout things but overall there isn't a ton of css to write

never have long lines of text, this is a design thing, you always want to break it up into smaller columns and sections instead of having it stretch across the whole screen, this is where max-width comes into play


## Day 19 - Mobile Navigation Challenge

no new content, just challenge to make mobile friendly nav menu


## Day 20 - Mobile Navigation Challenge Solution

no new content just solution to day 19 challenge


## Day 21 - Final Challenge

Other Free Resource Links

Kevin Powell YouTube - https://www.youtube.com/kevinpowell
Kevin Powell HTML/CSS Crash Course - https://scrimba.com/course/ghtmlcss
Wes Bos CSS Grid Course - https://cssgrid.io/
FrontEnd Dev Courses - https://www.frontendmentor.io/
Brad Traversy YouTube - https://www.youtube.com/channel/UC29ju8bIPH5as8OGnQzwJyA
Web Dev Simplified YouTube - https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw
DesignCourse YouTube - https://www.youtube.com/user/DesignCourse
Program With Erik YouTube - https://www.youtube.com/channel/UCshZ3rdoCLjDYuTR_RBubzw
Florin Pop YouTube - https://www.youtube.com/c/florinpop
Dev Ed YouTube - https://www.youtube.com/channel/UClb90NQQcskPUGDIXsQEz5Q
Weibenfalk YouTube - https://www.youtube.com/user/Weibenfalk
Coder Coder YouTube - https://www.youtube.com/channel/UCzNf0liwUzMN6_pixbQlMhQ
James Q Quick YouTube - https://www.youtube.com/channel/UC-T8W79DN6PBnzomelvqJYw
Flavio YouTube - https://www.youtube.com/user/copesc
Colt Steele YouTube - https://www.youtube.com/channel/UCrqAGUPPMOdo0jfQ6grikZw/videos

Final Challenge is just a layout pdf to recreate from scratch
