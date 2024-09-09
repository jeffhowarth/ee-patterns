# __access geoMethods__

The geoMethods module is a collection of, well, methods that I wrote and packaged in a way that will allow you to use the methods without having to write them from scratch. 

Most of the methods in the module are in the module for two reasons:    

1. Each represents a recurring task of geospatial analysis that are supported by other geographic information systems (like QGIS or ArcGIS).

2. Each requires a chain of transformations to make in Earth Engine which can be conceptually confusing and technically difficult for novices to do.    

My hope is that the module may help you focus on how different methods of spatial analysis and cartography work conceptually without having to get bogged down in writing complicated task chains for lower-level branches of task trees.  

## __import module__  

__To use geoMethods, create a container and require the module.__  

```js
var geo = require("users/jhowarth/eePatterns:modules/geoMethods.js");

print("geoMethods dictionary", geo.help);    // Prints dictionary of all tools in module.
```

This will print the module's help dictionary, which lists all methods and url links to their docs.

## __docs in eePatterns__  

__A globe icon :earth_americas: identifies methods from module.__  

In the METHODS documentation, the :earth_americas: symbol identifies a method that requires the geoMethods module. To use any of these methods, you will need to include the [import module](#import-module) in your script prior to calling the method. 

## __peak under hood__

__Add module to your READER tray if you want to see the underlying code to any method.__

The module only hides the data from you if you do not want to see it. If you would like to look under the hood, I have made the code for the module public and you can add it to the READER tray of the IDE by [__clicking here__](https://code.earthengine.google.com/?accept_repo=users/jhowarth/eePatterns){target=_blank}. 

---

<p xmlns:cc="http://creativecommons.org/ns#" >This work is licensed under <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY-NC-SA 4.0<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1" alt=""></a></p>