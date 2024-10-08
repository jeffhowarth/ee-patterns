__PRACTICE 3__

# _**Parent materials of soils**_  

## __purpose__  

Your goal is to make a map that could help town planners in Addison County compare information from the Addison County Soil Survey (1971) to property parcels in their town.  

Practically, your workflow will include the following patterns:  

* gather and inspect vector data  
* filter feature collections  
* convert vector to raster  
* mask raster data 
* display layer of nominal classes with unique colors 
* explain nominal class symbology    
* filter and flatten an image collection  
* make terrain layers 
* paint strokes    

When you solve the problem, you should have a workflow that uses the town of Middlebury as the test subject to produce a map with the layers shown in the app below. Ideally, you will write the script so that you can very easily shift the map to any other town in Addison County, Vermont.   

---

<iframe
  src="https://ee-patterns.projects.earthengine.app/view/practice-03"
  style="width:854px; height:854px"
></iframe>  

[_open app in new tab_](https://ee-patterns.projects.earthengine.app/view/practice-03){target=_blank}

---

## __data sources__  

We will use a number of datasets that are available through the cloud, either through the Earth Engine Data Catalog or assets that I maintain for Vermont geography.  

<center>

| DATA                  | DESCRIPTIONS                                                              |
| :--                   | :--                                                                       |
| US Counties           | [source][counties]{target=_blank}<br>[background][tiger]{target=_blank}   |
| VT Towns              | [source][towns]{target=_blank}                                            |
| VT Parcels            | [source][parcels]{target=_blank}<br>[background][parcel-program]{target=_blank} |
| VT Soils              | [source][soils]{target=_blank}<br>[background][vt-nrcs]{target=_blank}<br>[report][soils-report]{target=_blank}  |
| DEM 1m                | [source][DEM]{target=_blank}<br>[background][3dep]{target=_blank}         |  

</center>

---  

## __starter script__    

```js
var geo = require("users/jhowarth/eePatterns:modules/geo.js");

print("geo methods dictionary", geo.help);    // Prints dictionary of all tools in module.  
print("geo palettes", geo.iPalettes);         // Prints dictionary of all palettes in module. 


// -------------------------------------------------------------
//  DATA SOURCES 
// ------------------------------------------------------------- 

var fc_address_county = "TIGER/2018/Counties";
var fc_address_town = "projects/conservation-atlas/assets/cadastre/Boundary_TWNBNDS_poly";
var fc_address_parcel = "projects/vt-conservation/assets/state/FS_VCGI_OPENDATA_Cadastral_VTPARCELS_poly_standardized_parcels_SP_v1";
var fc_address_soils = "projects/conservation-atlas/assets/soils/VT_Data_NRCS_Soil_Survey_Units";
var ic_address_dem = "USGS/3DEP/1m"; 

var palette_soils = geo.iPalettes.iSoils.parent_materials_addison_county;
var class_labels_soils = geo.iPalettes.iSoils.parent_materials_addison_county_labels;

print("SOILS Palette and Class labels", palette_soils, class_labels_soils);

// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
//  1. GATHER HUMAN GEOGRAPHY
// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

// -------------------------------------------------------------
//  1.1 Make Addison County layer
// -------------------------------------------------------------

var fc_county ;

// -------------------------------------------------------------
//  1.2 Make study town (Middlebury) layer
// -------------------------------------------------------------

var fc_town ;

// -------------------------------------------------------------
//  1.3 Center map on study town
// -------------------------------------------------------------



// -------------------------------------------------------------
//  1.4 Make parcels in study town layer
// -------------------------------------------------------------

var fc_parcels ;



// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
//  2. GATHER SOILS DATA AND FILTER FOR ADDISON COUNTY 
// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

// -------------------------------------------------------------
//  2.1 Gather soils data
// -------------------------------------------------------------


var fc_soils ;



// -------------------------------------------------------------
//  2.2 Filter for soils that overlap Addison County
// ------------------------------------------------------------- 

var fc_filter_bounds_soils ;

// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
//  3. MAKE PARENT MATERIAL IMAGE FOR STUDY TOWN. 
// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

// -------------------------------------------------------------
//  3.1 Make nominal image of soil parent material. 
// -------------------------------------------------------------

var image_nominal_soils ;

// -------------------------------------------------------------
//  3.2 Mask by Addison County.
// -------------------------------------------------------------

var image_with_mask_soils ;

// -------------------------------------------------------------
//  3.3 Display masked soils image as layer. 
// -------------------------------------------------------------



// -------------------------------------------------------------
//  3.4 Add legend to bottom-left of Map. 
// -------------------------------------------------------------



// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
//  4. GATHER DEM 
// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

// -------------------------------------------------------------
//  4.1 Construct image collection. 
// -------------------------------------------------------------

var ic_dem ;

// -------------------------------------------------------------
//  4.2 Filter for images that overlap Addison County.
// -------------------------------------------------------------

var ic_filtered_dem_county ;

// -------------------------------------------------------------
//  4.3 Mosaic filtered image collection to image. 
// -------------------------------------------------------------

var ic_dem_mosaic ;


// -------------------------------------------------------------
//  4.2 Mask mosaic image by Addison County. 
// -------------------------------------------------------------

var image_with_mask_dem ;

// -------------------------------------------------------------
//  4.3 Make hillshade from masked image and display as layer with 0.5 opacity.
//  No vertical exaggeration; azimuth 315; zenith 35.
// -------------------------------------------------------------

var hs  ;

// -------------------------------------------------------------
//  4.6 Make slope from masked image and display as layer with 0.5 opacity.
// -------------------------------------------------------------

var slope ;


// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-
//  5. PAINT STROKES
// -+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-

// -------------------------------------------------------------
//  5.1 Make strokes for parcels ("white" and 0.5 weight) and add as layer.
// -------------------------------------------------------------

var strokes_parcels ;

// -------------------------------------------------------------
//  5.2 Make strokes for town ("white" and 4 weight) and add as layer.
// -------------------------------------------------------------

var strokes_town ;

// -------------------------------------------------------------
//  PRACTICE CHECKS
// -------------------------------------------------------------

print("CHECKS:");

//  Import check module for tutorial 1.

var check = require("users/jhowarth/eePatterns:checks/p03.js");

// ><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><

//  PLEASE DO THE FOLLOWING: 

// 1. Uncomment all of the check statements below.
// 2. Replace 'result_#p#' with the name of the data object that you used to map as a layer in each section.
// 3. Run the script.
// 4. Use the results printed to Console in the Check Up that is due Friday 5pm. 

// ><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><><

// check.checkCollection("Check 1.1", result_1p1);
// check.checkCollection("Check 1.2", result_1p2);
// check.checkCollection("Check 1.4", result_1p4);
// check.checkCollection("Check 2.1", result_2p1);
// check.checkCollection("Check 2.2", result_2p2);

// check.checkPoint("Check 3.3", result_3p3);
// check.checkPoint("Check 4.5", result_4p5);
// check.checkPoint("Check 4.6", result_4p6);



```


---

<p xmlns:cc="http://creativecommons.org/ns#" >This work is licensed under <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-NC-SA 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1" alt=""></a></p>  

[counties]: https://developers.google.com/earth-engine/datasets/catalog/TIGER_2018_Counties
[towns]: https://geodata.vermont.gov/datasets/VCGI::vt-data-town-boundaries-1/about  
[parcels]: https://geodata.vermont.gov/datasets/VCGI::vt-data-statewide-standardized-parcel-data-parcel-polygons-1/about
[soils]: https://geodata.vermont.gov/datasets/VCGI::vt-data-nrcs-soil-survey-units/about  
[DEM]: https://developers.google.com/earth-engine/datasets/catalog/USGS_3DEP_1m  

[tiger]: https://www.census.gov/programs-surveys/geography/guidance.html  
[parcel-program]: https://vcgi.vermont.gov/data-and-programs/parcel-program  
[vt-nrcs]:https://www.nrcs.usda.gov/conservation-basics/conservation-by-state/vermont/vermont-soils  
[soils-report]: https://archive.org/details/usda-general-soil-map-soil-survey-of-addison-county-vermont-1971  
[3dep]: https://www.usgs.gov/3d-elevation-program/
