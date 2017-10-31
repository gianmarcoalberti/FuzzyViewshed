# FuzzyViewshed

##Short Description
The toolbox (built under *ArcGIS 10.1*) provides the facility to calculate the Fuzzy Viewshed as proposed by `Ogburn 2006`, which modify the original proposal by Fisher. It produces a **Fuzzy Vieshed** raster in which, as customary in 'regular' (i.e., binary) viewshed rasters, 0 indicates cells that are not visible, 1 indicates cells that are visible. However, unlike binary viewshed, values between 0 and 1 correspond to a drop in visibility as function of the target distance AND target size. 

With reference to the equation proposed in `Ogburn 2006, p. 410`, the user may want to input the value of *b1* (which is set by default to 1000 m, i.e. 1 km, as suggested by Fisher and Ogburn), while the value of the parameter *b2* is internally calculated by the toolbox. It is worked out multiplying the target object height (in meters) by a distance multiplier (3440, derived from the equation in `Ogburn 2006, p. 410` top) corresponding to a visual arc of 0.01667 degrees (=1 arc-minute). The parameter *b1* is then subtracted from that value (following `Ogburn 2006, p. 412`), so eventually devising the value for *b2*.

Following literature, the parameter *b1* represents the distance from the observer within which there is not drop in visibility, i.e. the visibility is not affected by the distance. Parameter *b2* represents the distance from *b1* within which there is a drop in visibility of 50%, i.e. at the end of the distance b2 visibility has dropped by 50%. Beyond *b2*, the visibility drops continuously by the remaining 50% till reaching 0.

Other parameters input by the user are: a `Digital Terrain Model`, the `point shapefile` containing the observer location, the processing extent (must be equal to the extent of the input DTM), the output Fuzzy Viewshed `cell size` (equal to the cell size of the input DTM), the `folder name and location` where the output files will be saved. 
The Fuzzy Viewshed raster is given the following name: `fuzzy_VS`.

### Reference
`Ogburn E. D. 2006. Assessing the level of visibility of cultural objects in past landscapes. Journal of Archaeological Science 33, 405-416`


## Data input
Data are fed into the toolbox via its **control panel**, which is depicted in the following figure. For easiness of use, each field is accompanied by a short help documentation.
[![screenshot_01.png](https://s1.postimg.org/3c6y0akopb/screenshot_01.png)](https://postimg.org/image/9jic0ggft7/)


## Installation
As shown below, the toolbox can be quite easily installed. It suffices o right-click on top of the ArcGIS’ toolbox tree, then select ‘add Toolbox’ from the pop-up menu, and then navigate through your PC folders to select the ‘FuzzyViewshed.tbx’ file.
[![screenshot_02.png](https://s1.postimg.org/67dni2xndr/screenshot_02.png)](https://postimg.org/image/6w6x23l6e3/)


## Example
The following image is the Fuzzy Viewshed produced by the toolbox. The observer point is a location near Mount Etna (Sicily). The observer point’s parameters are 1.7m (observer height, or OFFASET A in ArcGIS terms), 3m (target height, or OFFSET B). For the purposes of the Fuzzy Viewshed calculation, the target object size (i.e., height) is set to 3m.
[![Untitled.jpg](https://s1.postimg.org/60n70t5cz3/Untitled.jpg)](https://postimg.org/image/7htc2k9hpn/)

