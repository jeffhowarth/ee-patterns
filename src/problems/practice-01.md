__PRACTICE 1__

# _**Memory under cover**_  

## __goal__  

Your goal is to import a digital elevation model (DEM), make a Map with the five layers shown in the app below, and then use these layers to interpret the four POI.

<iframe
  src="https://ee-patterns.projects.earthengine.app/view/practice-01"
  style="width:854px; height:854px"
></iframe> 

[_open app in new tab_](https://ee-patterns.projects.earthengine.app/view/practice-01){target=_blank}

---   

## __starter script__  

```js

// -------------------------------------------------------------
//  Access image from this cloud address:
//  "projects/ee-patterns/assets/p01/chipmanHill_2023_35cm_DEMHF"
// -------------------------------------------------------------

var image ;


// -------------------------------------------------------------
//  Customize Map. 
// -------------------------------------------------------------

// Set map center and zoom level.


//  Set basemap style to hybrid.


// -------------------------------------------------------------
//  Display image as a map layer;
//  Stretch layer display values over image data range.
// -------------------------------------------------------------



// -------------------------------------------------------------
//  Multiply the elevation values by 2 (apply a scalar operation)
//  and then derive slope of this surface.
// -------------------------------------------------------------

var image_slope ;

// -------------------------------------------------------------
//  Display slope image as a map layer;
//  Stretch layer display values over image data range.
//  Display so that "steeper is darker".
// -------------------------------------------------------------



// -------------------------------------------------------------
//  Multiply the elevation values by 2 (apply a scalar operation)
//  and then calculate the hillshade of this surface. 
// -------------------------------------------------------------

var image_hs ;

// -------------------------------------------------------------
//  Using the original elevation surface (without a scalar applied),
//  calculate the deviation from mean elevation;
//  Use 10 as the distance argument.
//  Try to display the layer with this palette: ['blue', 'white', 'red']
// -------------------------------------------------------------

var image_dme ;


// -------------------------------------------------------------
//  PRACTICE CHECKS
// -------------------------------------------------------------

//  I. QUANTITATIVE 

print("QUANTITATIVE CHECKS:");

//  Import check module for tutorial 1.
//  Uncomment the line below.

var check = require("users/jhowarth/eePatterns:checks/p01.js");

//  Uncomment the three lines below, run script, and look at the results in Console. 

// check.checkPoint("CP1:", image_slope);
// check.checkPoint("CP2:", image_hs);
// check.checkPoint("CP3:", image_dme);

//  II. QUALITATIVE  

//  Use zoom to inspect locations marked A, B, C, D.
//  For each letter, please write down:

//    1. What do you think the linear feature marked by the letter "is"?
//    2. Why?

//  When you have completed this practice problem, please take the short quiz on Canvas where you will report your results. 



```

---  

<p xmlns:cc="http://creativecommons.org/ns#" >This work is licensed under <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-NC-SA 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1" alt=""></a></p>