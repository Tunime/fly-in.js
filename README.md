# fly-in.js
a jQuery plugin that animates DOM elements sliding in as you scroll down the page.

## Installation

This plugin requires JQuery. Copy and paste the line below to include it.
 
`<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>`

After that, include fly-in.min.js

`<script src="PATH/TO/FLY-IN.JS"></script>`

## Usage

### Requirements
fly-in.js looks for an element with the id of 'runway'. You must wrap the runway element around all the elements that you want to animate, so that it is the parent element of all flyers. 

Here is the easiest way to do this:

```
<html>
  <head>
    <title>Test Flight</title>
  </head>
  <body>
    <div id="runway">
      ...flyers go here...
    </div>
  </body>
</html>
```

### Examples

*Basic Usage:*
Simply add the class that you want the element to fly in from.
```
<div class='fly-in-left'>I will fly in from the left!</div>
<div class='fly-in-right'>I will fly in from the right!</div>
```

### Options
Currently the only options that are supported are: 
- `speed`
- `transition-timing-function`

**Speed:**
Allows you to set the amount of time it will take to animate in seconds.
Default is `1`
```
<div class='fly-in-left' data-speed="5">slow</div>
<div class='fly-in-right' data-speed="0.5">fast</div>
```

**Animation-timing-function:**
Allows you to choose the css animation timing function. A list of valid functions can be found [here](http://www.w3schools.com/cssref/css3_pr_transition-timing-function.asp).
Default is `linear`
```
<div class='fly-in-right'data-transition-timing-function="linear">linear</div>
<div class='fly-in-left'data-transition-timing-function="ease-in-out">ease-in-out</div>
```

## Misc
Fly-in.js moves elements with the class of fly-in-right and fly-in-left offscreen before the page loads, and monitors how far down the page the user has scrolled. Once there is room for the element on the page, it animates a fly-in from the appropriate side. 

Fly-in.js also monitors when the bottom fly-in element has animated. If the user has refreshed the page half-way down the page, and there are any elements that have not flown in by the time the bottom fly-in element has animated, then the remaining elements are brought back, so monitoring can stop. This was done purely to boost performance. 

## Demo

[Demo](http://mckaysmalley.com/ski_survey/)
