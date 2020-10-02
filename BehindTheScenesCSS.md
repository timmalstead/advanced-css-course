a rule is a selector and a declration block

the cascade reolves declarations that conflict

## the cascade is the process of combining different stylesheets and resolving conflicts between css rules and declarations when more than one rule applies to a certain element

author declarations, user declarations, user agent (browser) declarations

### importance of declarations

user !important > author !important > author > user > browser

### prcedence of specificity

inline styles > ids > classes, pseudo-classes, attributes > elements, pseudo-elements

specifity scoring!

4 numbers, organized as follows

{
inline: num,
ids: num,
classes: num,
elements: num
}

---

.class {
inline: 0,
ids: 0,
classes: 1,
elements: 0  
}

---

ele#id ele.class .otherclass {
inline: 0,
ids: 1,
classes: 2,
elements: 2  
}

---

ele {
inline: 0,
ids: 0,
classes: 0,
elements: 1  
}

#id ele.class:pseudoclass {
inline: 0,
ids: 1,
classes: 2,
elements: 1
}

in the example above we go from left to right and the second element has the most

but not just the biggest score total, the biggest number weighted left to right

this is called the cascaded value

## source order

last decration written in code then applies

got it? goes by order of declrations, if needed moves on to specificty and then if needed moves on to source order

the universal selector \* has NO specifity value i.e.

\* {
inline: 0,
ids: 0,
classes: 0,
elements: 0
}

don't rely on !important at one end or on order at the other. when using static stylesheets, the real work happens in the specifity

order DOES matter, however, when dealing with multiple stylesheets.

say you find yourself transported to 2010 and you need to import a reset stylesheet, you should import BEFORE your own stylesheet so that your styles can override the third party styles where they conflict

## value processing

all units em,vh etc are converted to pixels

i think that i am going to start declaring a base font size in pixels and then referencing it with rem. it's just easier.

i have conducted an experiment and that does indeed work like that. wouldn't be surprised if i started working with rems for text and ems for lengths, with percentages and vw/vh as needed

## inheritance

each css property has a value, remember that
if a value in inheritable, check mdn, than the value that gets inherited is the COMPUTED value. so whatever it is for the parent value in absolute terms it will be for the child value

if a value is NOT inheritable, it will default to its initial value

there of course is an `initial` keyword, but I did not know there is an `inherit` keyword. i'm interested to learn how that works.

## px to rem workflow`

we want to change px to rem to have a simple way to change settings on the page

root font size is set in the html selector

you can set it as a percentage in the html tag and base your rems off of that. the absolute value it is referencing is the USER style sheet. Most don't mess with this but some, like those with eyesight issues for example, may change this and in that case your rems will take that into account.

## visual formatting model

after the cascade and computed values, after the dom and cssom have been combined, we have the final stage of the rendering process

css will calculate all the boxes, z indexes, computed values and all of that good stuff and layout your pages

worth remembering that `box-sizing: border-box;` is meant to have the total `width` and `height` you set include the padding and border, not just the content.

reference the block, inline-block and inline differences frequently. that's something that is so foundational you really should know it without thinking.

here's an interesting fact about stacking elements that I did not know: elements below, on a z index for example, are painted before those higher ups

## architechture, components, BEM

Okay, mostly see the sliders for this one

I don't know how I feel about BEM. It seems like a lot of trouble. Could be worth it?
