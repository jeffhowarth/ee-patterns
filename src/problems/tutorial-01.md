__TUTORIAL 1__

# _**A sketch map from lidar**_   

## __goal__  

In this tutorial, our practical goal is to import a digital surface model (DSM) from this address:

```js
"projects/ee-patterns/assets/t01/Elevation_DSM0p7m2017_cm"
```

and make a map with the layers shown below.  

<iframe
  src="https://ee-patterns.projects.earthengine.app/view/tutorial-01"
  style="width:854px; height:854px"
></iframe>  

[_open app in new tab_](https://ee-patterns.projects.earthengine.app/view/tutorial-01){target=_blank}


--- 

## __starter script__  

```js
// -------------------------------------------------------------
//  Construct image data object from address.
// -------------------------------------------------------------

var image ;

// -------------------------------------------------------------
//  Print properties of image to the Console. 
// -------------------------------------------------------------



// -------------------------------------------------------------
//  Set map center and zoom level.
// -------------------------------------------------------------



// -------------------------------------------------------------
//  Set basemap style.
// -------------------------------------------------------------



// -------------------------------------------------------------
//  Display image as a map layer.
// -------------------------------------------------------------



// -------------------------------------------------------------
//  Import geoMethods module. 
// -------------------------------------------------------------



// -------------------------------------------------------------
//  Set viz range to data range.
// -------------------------------------------------------------

var image_min_max ;



// -------------------------------------------------------------
//  Chart histogram of image data values.
// -------------------------------------------------------------

var image_histogram ;


// -------------------------------------------------------------
//  Apply scalar operation; 
//  convert image data from centimeters to meters.
// -------------------------------------------------------------

var image_meters ;

// -------------------------------------------------------------
//  Display new image as a layer
//  with viz range set to data range.
// -------------------------------------------------------------


// -------------------------------------------------------------
//  Derive slope of the surface image. 
// -------------------------------------------------------------

var image_slope ;

// -------------------------------------------------------------
//  Display slope image as map layer so that "steeper is darker".
// -------------------------------------------------------------



// -------------------------------------------------------------
//  TUTORIAL CHECKS
// -------------------------------------------------------------

//  I. QUANTITATIVE 

//  Import check module for tutorial 1.

var check = require("users/jhowarth/eePatterns:checks/t01.js");

//  Uncomment the four lines below, run script, and look at the results in Console. 

// print("QUANTITATIVE CHECKS:");
// check.checkPoint("CP1:", image);
// check.checkPoint("CP2:", image_meters);
// check.checkPoint("CP3:", image_slope);

//  II. QUALITATIVE  

//  Use zoom to inspect locations marked A, B, C, D.
//  For each letter, please write down:

//    1. What do you think the location "is"?
//    2. How does the location represent environmental change?

//  We will discuss in next lecture. 



```

---

<p xmlns:cc="http://creativecommons.org/ns#" >This work is licensed under <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-NC-SA 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1" alt=""></a></p>