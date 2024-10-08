__TUTORIAL 2__

# _**A slippy topographic map**_  

## __goal__  

In this tutorial, our practical goal is to import a digital elevation model (DEM) from this address:

```js
'USGS/3DEP/10m'
```

and make a map with the layers shown below.  

<iframe
  src="https://ee-patterns.projects.earthengine.app/view/tutorial-02"
  style="width:854px; height:854px"
></iframe>  

[_open app in new tab_](https://ee-patterns.projects.earthengine.app/view/tutorial-02){target=_blank}

## __starter script__

```js
// Require geo module. 

var geo = require("users/jhowarth/eePatterns:modules/geo.js"); 

print("geo dictionary", geo.help);      // Prints dictionary of all tools in module.
print("geo palettes", geo.iPalettes);   // Prints dictionary of all palettes in module. 

// -------------------------------------------------------------------------------
//  Area of interest for tutorial.
// -------------------------------------------------------------------------------

var aoi = geo.aoi.t2;

print("Area of interest", aoi);

// -------------------------------------------------------------------------------
//  MAP
//
//  Center map on aoi at zoom level 10. 
//  Set basemap to hybrid.
// -------------------------------------------------------------------------------



// -------------------------------------------------------------------------------
//  DEM
//
//  Gather raster from this address: 'USGS/3DEP/10m'
//  Display the image with stretch enhancement. 
//  Do not show the image by default. 
// -------------------------------------------------------------------------------

var image ;

// -------------------------------------------------------------------------------
//  SLOPE
//
//  Derive slope of a surface in degrees from elevation in meters from DEM.
//  Display the image with stretch enhancement. 
// -------------------------------------------------------------------------------

var image_slope ;


// -------------------------------------------------------------------------------
//  HILLSHADE
//
//  Derive hillshade from DEM.
//  Display as layer. 
// -------------------------------------------------------------------------------

var image_hs ;

// -------------------------------------------------------------------------------
//  ASPECT
//
//  Derive aspect from DEM.
//  Display image as pseudo-color layer with palette: geo.iPalettes.iAspect.cyclical
//  Add legend aspect image (continuous data) to 'bottom-left' of Map.
//  Do not show the image by default. 
// -------------------------------------------------------------------------------

var image_aspect ;


// -------------------------------------------------------------------------------
//  ASPECT, part 2
//
//  Make a boolean image where all pixels not equal to 0 are true.
//  Display boolean image as a map layer.
//  Do not show the image by default. 

//  Mask all pixels in aspect image that are equal to 0.
//  Display masked image as a map layer. 
//  Do not show the image by default. 
// -------------------------------------------------------------------------------

//  Make a boolean (true/false) image based on a criterion.

var aspect_neq_0 ;

// -------------------------------------------------------------------------------
//  ASPECT, part 3
//
//  Reclassify the aspect image by equal intervals (22.5).
//  Remap the image to represent N, NE, E, SE, S, SW, W, NW categories. 
//  Display remapped image as a pseudo-color layer with palette: geo.iPalettes.iAspect.nominal
//  Add legend to the bottom-left corner of Map.
// -------------------------------------------------------------------------------

//  Reclassify by equal intervals.

var image_aspect_reclassified ;

//  Remap values. 

var image_aspect_remapped ;

// -------------------------------------------------------------------------------
//  ADD AOI ON TOP OF MAP
// -------------------------------------------------------------------------------

Map.add(geo.aoi.t2_layer);


```

---

<p xmlns:cc="http://creativecommons.org/ns#" >This work is licensed under <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-NC-SA 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1" alt=""></a></p>