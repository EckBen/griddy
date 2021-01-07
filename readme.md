
figure out github pages to display demo link

push to github







# Griddy
#### By: Ben Eck


## What it is
Griddy is a framework built on CSS Grid to provide a simple, fast, and responsive solution for website prototyping and production.
It was created using inspiration from Bootstrap framework in response to a project prompt from [The Odin Project](https://www.theodinproject.com/courses/html-and-css/lessons/design-your-own-grid-based-framework "Project Page").
***
## Features
### Some Perks
- Having been built on CSS Grid, each element can use the normal grid functionality, __container__ elements having the `display: grid;` attribute and it's children being the grid cells.
- Styling classes given to the __container__ element apply to all children, resulting in quick and easy bulk styling.
- The framework was built using Dart SASS. It is easily customizable, so long as you have a SASS compiler to use.

### Some Gotchas
- All column elements must be __div__ elements.
- To use borders you must set __bor-w-\*__, __bor-c-\*__, and __bor-s-\*__. If you leave one out the border will not show.
***
## Requirements
There are two ways to use this framework.
1. __No requirements__: To use the full framework with no customization you can download and import the __griddy.css__ file from the __/css__ directory. This is a precompiled stylesheet that contains the entire framework and is, therefore, quite long. It is recommended that you use option 2 if possible.
2. __Requires SASS compiler__: If you have the ability to compile __.scss__ files this is the option for you! After you clone the repository open __/config/_config.scss__. This file contains all of the variables that are used to generate classes for the framework. You can customize it by following the documentation below. By doing this you can greatly reduce the amount of CSS code generated.
***
## Usage
Once you have a __griddy.css__ file and it is imported to your project, usage is simple. First, set a parent __div__ with __class="container"__. Inside this container set as many __div__ as you would like with __class="c-1"__ through __class="c-12"__. That's it!

### Container specific classes
Each of these classes cascade to the columns within the container they are set on. They will not work anything without __container__ class.

- __.gap-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Sets grip gap attribute to __\*__. Default values for __\*__ are even numbers from 0 through 100. Units: __px__.
- __.m-__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Default values for margin are 0 through 50 in increments of 5. Units: __px__.
  - __.m-\*__ :&nbsp; &nbsp; &nbsp; &nbsp;Sets all margins to __\*__.
  - __.m-l-\*__ :&nbsp; &nbsp; Sets left margin to __\*__.
  - __.m-r-\*__ :&nbsp; &nbsp; Sets right margin to __\*__.
  - __.m-lr-\*__ :&nbsp; &nbsp;Sets left and right margin to __\*__.
  - __.m-t-\*__ :&nbsp; &nbsp; Sets top margin to __\*__.
  - __.m-b-\*__ :&nbsp; &nbsp; Sets bottom margin to __\*__.
  - __.m-tb-\*__ :&nbsp; Sets top and bottom margin to __\*__.

### Div specific classes
- __.empty__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Clears any styling that was set by on the container.
- __.c-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Declares __div__ as a column that span __\*__ number of columns. Values are 1 through 12. This represents the number of twelfths of the __container__ width that the __.c-\*__ will occupy.

### Classes that work on both
When these classes are set on both a __container__ and a __.c-\*__ the class set on the __.c-\*__ takes precedence.

- __.bg-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Sets background color. Default values for __\*__ can be found below in __$colors__.
- __.bor-c-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Sets border color. Default values for __\*__ can be found below in __$colors__.
- __.bor-s-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Sets border style. Default values for __\*__ can be found below in __$borders__.
- __.bor-w-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Sets border width. Default values for __\*__ are 0 through 15. Units: __px__.
- __.bor-rad-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Sets border radius for all corners. Default values for __\*__ are 0 through 20. Units: __px__.
- __.bor-rad-circle__ :&nbsp; Sets border radius for all corners to 50%. To ensure a circular shape make sure your __div__ height and width will be equal.
- __p-__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Default values for padding are even numbers from 0 through 20. Units: __px__. 
  - __p-l-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Sets padding-left to __\*__.
  - __p-r-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Sets padding-right to __\*__.
  - __p-lr-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; Sets padding-left and padding-right to __\*__.
  - __p-t-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Sets padding-top to __\*__.
  - __p-b-\*__ :&nbsp; &nbsp; &nbsp; &nbsp; Sets padding-bottom to __\*__.
  - __p-tb-\*__ :&nbsp; &nbsp; &nbsp; &nbsp;Sets padding-top and padding-bottom to __\*__.
- __t-em-\*__ :Sets font-size. Units: __em__.
- __t-rem-\*__ :Sets font-size. Units: __rem__.
- __t-a-\*__ :Sets text-align to __\*__. Default values for __\*__ can be found below in __$alignments__.
- __t-c-\*__ :Sets color for text to __\*__. Default values for __\*__ can be found below in __$colors__.

### Classes that can except breakpoints
- __.c-\*__
- __.gap-\*__
- __.m-__
- __.p-__
- __t-em-\*__
- __t-rem-\*__

Breakpoints are work as minimum-widths, so setting a __-lg__ breakpoint would only take effect if the browser width is over __992px__.

These classes (and their descendents in the cases of __.m-__ and __.p-__) can be set as either general classes or as breakpoint classes. To set them as general classes, set them as stated above. For example, `class="gap-20"` will set the grid gap to __20px__. This rule would remain no matter the size of the browser window. To set them as breakpoint classes, add a hyphen and the breakpoint name that you wish to use to the end of the normal class. For example, `class="gap-20-lg"` will set the grid gap to __20px__, but only if the browser width is above __992px__. Multiple classes can be added to a __.c-\*__ or __container__. The rules will over write each other based on the browser width. For example, `class="gap-4 gap-10-md gap-20xlg"` would make the grid gap 4px when the browser is 0px-767px wide, 10px when the browser is 768px-1199px wide, and 20px when the browser is 1200px or greater.

### Breakpoint Sizes
- __$breaks__
  - __-xs__ : &nbsp; &nbsp; &nbsp;0px-575px.
  - __-s__ : &nbsp; &nbsp; &nbsp; &nbsp;576px-767px.
  - __-m__ : &nbsp; &nbsp; &nbsp; 768px-991px.
  - __-lg__ : &nbsp; &nbsp; &nbsp; 992px-1199px.
  - __-xlg__ : &nbsp; &nbsp; 1200px-1399px.
  - __-xxlg__ : &nbsp; 1400px and above.

### Default values
- __$borders__
  - __none__ :&nbsp; &nbsp; &nbsp; &nbsp; none
  - __hidden__ :&nbsp; &nbsp; &nbsp;hidden
  - __dotted__ :&nbsp; &nbsp; &nbsp;dotted
  - __dashed__ :&nbsp; &nbsp; dashed
  - __solid__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;solid
  - __double__ :&nbsp; &nbsp; double
  - __groove__ :&nbsp; &nbsp; groove
  - __ridge__ :&nbsp; &nbsp; &nbsp; &nbsp; ridge
  - __inset__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;inset
  - __outset__ :&nbsp; &nbsp; &nbsp; outset
- __$colors__
  - __red__ :&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; rgb(255,0,0)
  - __blue__ :&nbsp; &nbsp; &nbsp; &nbsp; rgb(0,0,255)
  - __green__ :&nbsp; &nbsp; &nbsp;rgb(0,255,0)
  - __black__ :&nbsp; &nbsp; &nbsp; rgb(0,0,0)
  - __gray__ :&nbsp; &nbsp; &nbsp; &nbsp; rgb(110,110,110)
  - __white__ :&nbsp; &nbsp; &nbsp; rgb(255,255,255)
  - __mango__ :&nbsp; &nbsp;#FFBE0B
  - __orange__ :&nbsp;  #FB5607
  - __pink__ :&nbsp; &nbsp; &nbsp; &nbsp;#FF006E
  - __violet__ :&nbsp; &nbsp; #8338EC
  - __azure__ :&nbsp; &nbsp; &nbsp;#3A86FF
- __$alignments__
  - __-c__ :&nbsp;  center
  - __-l__ :&nbsp;  left
  - __-r__ :&nbsp;  right
  - __-j__ :&nbsp;  justify
***
## How to customize the framework
In order to customize this framework you must have a SASS compiler!

Open __/config/\_config.scss__. This file contains all of the variables used to generate classes.

You can easily change the list of defaults stated above by simply adding, removine, or altering them as you see fit. It is recommended that you remove anything not in use before compiling your final __.css__ to minimize the file size.

Below the lists, you will see groups of variables. Narrowing the range or increasing increment size will greatly reduce file size, but keep in mind that the only usable numbers for the classes are ones generated from these variables. For example, if __\$bor-radius-min__=5 and __$bor-radius-max__=7, the only usable numbers for border radius would be 5, 6, and 7.

__\$gap-\*__, __\$margin-\*__, and __\$padding-\*__ generate their sizes using increments. The class names available for each match the sizes calculated using the increments and ranges set. This means that the actual class names are each integer in the range times the increment. For example, if __\$gap-min__=5, __\$gap-max__=7, and __\$gap-increment__=5, the usable class names would be __.gap-25__, __.gap-30__, and __.gap-35__.

__\$font-size-\*__ generates classes using a similar technique, but keeps the naming scheme consistant no matter what values you input. The numbers for usable class names will always be integers from 1 through the value of __\$font-size-number-of-steps__. The actual values will be the number of steps worth of increments from the base value. For example, if __\$font-size-base__=1, __\$font-size-increment__=0.5, and __\$font-size-number-of-steps__=3, the usable class names with their values would be as follows:

- __.t-em-1__ : 1 em
- __.t-em-2__ : 1.5 em
- __.t-em-3__ : 2 em
- __.t-rem-1__ : 1 rem
- __.t-rem-2__ : 1.5 rem
- __.t-rem-3__ : 2 rem
***
## Demo
There is a picture of a demo page [here](../framework/demos/demo.png).

For an active demo, run __demo.html__ in your browser. It highlights the different things that can be done with this framework and the __.html__ file can be used as a reference for how to use the framework.

Enjoy!!!