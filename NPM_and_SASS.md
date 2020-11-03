## Sass

Sass is fine. Npm is great.

Sass is a preprocessor

Things like variables

nesting etc.

This is fine, although i don't know that I will become a sass convert. I think it will help with my styled components code

this is SCSS syntax, closer to original css syntax that we'll be using. i don't think i've used that before

oh, i do know this. i guess scss syntax is what's used in styled components

this is fine. it's pretty much just styled components syntax to me

This is all done with a codepen so don't go crazy looking for a file

## Mixins

reusable line of code

@mixin mixin-name {
css delcaration and rules
}

we use by typing @include mixin-name

oh wow,looks like you can do arguments with mixins as well. like for different colors and what not

@mixin mixin-name(\$color) {
color: \$color
}

element {
@include mixin-name(\$my-color)
}

mixins! use em with or without arguments

## functions

there are sass specific and vanilla css specific functions

you can write sass functions but not vanilla css functions

here's the syntax

@function divide($arg-a,$arg-b) {
@return $arg-a / $arg-b
}

element {
margin: divide(40,2) \* 1px;
}

## extends

%set-of-rules {
color:black;
font-size: 2rem;
}

element {
@extend %set-of-rules
}

so, from what i can gather, this works like a mixin but not exactly. instead of taking the code and copying it into a block of css code like a mixin does, it does the opposite and moves the selctors into a central block of code with the rules.

That's fine. and if you need to do on block of code for a lot of selectors, i suppose that makes sense. ????

## command line

i command you to use the command line, because it's dope

## sass and npm

make sure node is all installed well, and npm i node-sass as a dev dependency

execute node-sass like this: node-sass ./sass/main.scss ./css/style.css -w

## auto reload

use the live-server package. it's a good option for static html/css/js
