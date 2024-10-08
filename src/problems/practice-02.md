__PRACTICE 2__

# _**Ice age bathtub**_  

## __goal__  

Your goal is to import a digital elevation model (DEM) and make a Map with the four layers shown in the app below. When you have finished solving the problem (or when the clock is approaching <mark>__5pm on Friday__</mark>), please work through the check-up on Canvas as best you can. 

<iframe
  src="https://ee-patterns.projects.earthengine.app/view/practice-02"
  style="width:854px; height:854px"
></iframe> 

[_open app in new tab_](https://ee-patterns.projects.earthengine.app/view/practice-02){target=_blank}

---   

## __starter script__  

```js
var geo = require("users/jhowarth/eePatterns:modules/geo.js");

print("geo methods dictionary", geo.help);    // Prints dictionary of all tools in module.
print("geo palettes", geo.iPalettes);         // Prints dictionary of all palettes in module.  

// -------------------------------------------------------------------------------
//  Gather image from "projects/ee-patterns/assets/p02/NOAA-CoNED-SOCAL".
//  Print a histogram - do you see land vs ocean floor in the histogram?
// -------------------------------------------------------------------------------

var image = ee.Image("projects/ee-patterns/assets/p02/NOAA-CoNED-SOCAL");

print("Image", image);


// -------------------------------------------------------------------------------
//  Area of interest for practice problem.
// -------------------------------------------------------------------------------

var aoi = image.geometry();


// Center map on aoi at zoom level 9 and set base layer to hybrid.




// -------------------------------------------------------------------------------
//  Apply a vertical exageration (z-factor) of 2 to elevation data for hillshade. 
//  Make a hillshade from this image and display the hillshade image as layer on Map.
// -------------------------------------------------------------------------------

var image_ve ;

var image_hs ;


// -------------------------------------------------------------------------------
//  Separate the original elevation image (without vertical exageration) into two different images:

//  (1) land elevations
//  (2) ocean floor elevations (bathymetry)

//  Each image should only store land or bathymetry elevation values, respectively.
//  All other values should be masked.
// -------------------------------------------------------------------------------

var image_land ;

var image_bathy ;

// -------------------------------------------------------------------------------
//  Reclassify the bathymetry image at 100 meter intervals. 
//  Display the reclassified image as layer on Map with 0.5 opacity.
//  To improve contrast, set max of viz dictionary such that all locations less than -2000 m (or class 20) are the darkest blue in palette.
//  Use this palette: geo.iPalettes.iBathy.eleven
// -------------------------------------------------------------------------------



var image_bathy_reclass ;



// -------------------------------------------------------------------------------
//  Define the Pleistocene shoreline as 130 meters lower than today's shoreline.
//  Make a boolean image that shows all land above ocean in Pleistocene.
//  Display boolean image as layer on Map with all non-land masked.
//  Set opacity of layer at 0.5.
// -------------------------------------------------------------------------------

var image_pleistocene ;


// -------------------------------------------------------------------------------
//  Reclassify the land image at equal 100 meter intervals. 
//  Display the reclassified image as layer on Map with 0.5 opacity.
//  Use this palette: geo.iPalettes.iHypso.bartholomew
//  Set opacity of layer at 0.5.
// -------------------------------------------------------------------------------

var image_land_reclass ;




// -------------------------------------------------------------
//  PRACTICE CHECKS
// -------------------------------------------------------------

//  I. QUANTITATIVE 

print("QUANTITATIVE CHECKS:");

//  Import check module for tutorial 1.

var check = require("users/jhowarth/eePatterns:checks/p02.js");

//  Uncomment the five lines below, run script, and look at the results in Console. 

// check.checkPoint("CP1:", image_hs);
// check.checkPoint("CP2:", image_land);
// check.checkPoint("CP3:", image_bathy);
// check.checkPoint("CP4:", image_pleistocene);
// check.checkPoint("CP5:", image_bathy_reclass);


```

---

## __advice on printing histograms__  

This is a BIG dataset. Whenever you print histogram or min-max values, set the scale to 30 and the extent to aoi.  

```js
print("Image histogram", geo.iCart.iHistogram(image, 30, aoi));
```

```js
print("Min & max value of image", geo.iCart.iMinMax(image, 30, aoi));
```

---  

## __check definitions__  

| VARIABLE            | DESCRIPTION                                                                                         |
| --:                 | :--                                                                                                 |
| image_hs            | Hillshade image from elevation data with vertical exaggeration of 2, azimuth 315, and zenith 35.    |   
| image_land          | Land elevations only. All sea floor elevations should be masked.                                         |
| image_bathy         | Sea floor elevations only. All land elevations should be masked. Include 0 elevation as sea floor. | 
| image_pleistocene   | _Flexible depending on how you solve this._ It could represent sea floor elevations when the sea-level was 130 meters lower than today, or you could skip this step and just define the boolean image. _Many different answers are potentially fine for this one and we will discuss in class on Monday._   |
| image_bathy_reclass | Modern sea floor (bathy) elevations reclassified into equal interval classes. |                                 |


---  

## __data sources__  

[CoNED](https://www.usgs.gov/special-topics/coastal-national-elevation-database-applications-project){target=_blank}  

[GEE Awesome Community Datasets](https://gee-community-catalog.org/projects/tbdem/){target=_blank}  

[CoNED Data Archive](https://topotools.cr.usgs.gov/topobathy_viewer/dwndata.htm){target=_blank}  

---

<p xmlns:cc="http://creativecommons.org/ns#" >This work is licensed under <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-NC-SA 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1" alt=""></a></p>