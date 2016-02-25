QGIS information processing
===
Tutorial
http://www.qgistutorials.com/

Get Climate data from
http://www.worldclim.org/

GeoTIFF data

Europe: covered by Tile 16
Australia: Tile 311 and 411
NA: Tile 12 & 13

Get mean, min and max temp (in Celcius), precipitation and altitude

—
Get country information (borders etc) from 
http://earthexplorer.usgs.gov/

—

Save latitude/longitude document with sample location names in tab-delimited file. Sometimes it is necessary to open it in TextWrangler and save as Unix encoding, UTF-8

—

**A) Read in sample locations**

1. Add delimited text layer
2. Select the text layer
3. Select for the X-field longitude and for the Y-field latitude
4. Select Coordinate Reference System WGS84
5. Right-click on the point layer and save as shapefile (shp)

**B) Get desired countries for analysis

1. Add vector layer
2. Select ne_10m_admin_0_countries.shp
3. Select ‘Select Single Feature’
4. Select all the countries you want
5. Right-click on ne_10m_admin_0_countries layer. Select ‘Save selection as..’. Name the output cra_boundaries.shp and make sure Add saved file to map box is checked. Click OK
. Right-click on ne_10m_admin_0_countries layer. Select ‘Remove’ (as this will take up too much working memory)
. 

**C) Merge and clip the climate data by the countries**

. Make sure that all the data you want to merge is in 1 folder and encopasses all the locations you are interested in (e.g. load them into QGIS first and see if they overlap the locations)
. Click ‘Raster>Miscellaneous>Merge
. In the dialog window, click 'Select…' next to 'Input files' Select all the subsets. Now click 'Select...' next to 'Output file' and name the output as you want. At the bottom, check the box next to Load into canvas when finished. Click OK. This can take some time!
. Go to Raster ‣ Extraction ‣ Clipper
. In the dialog window, select the above created layer as Input file and name as you want in the output (I did [climate_type]_cra in Climate_vars)
. In 'Clipping Mode', select 'Mask Layer' and select the boundary file created in **B**. Save as <filename>.tif 
. Check the box 'Load into canvas when finished' and click 'OK' (again can take a while).
. Remove the black pixels by right-click on layer, 'Properties', 'Transparancy', and set 'Additional no data value' to 0.
. Change the Min/Max value to more reasonable settings by adjusting this (still in the ‘Properties’ dialog) under ’Settings’ 
.Close QGIS

Still need to clip bio 1-14 to cra boundaries

**D) Load data into SAGA GIS**

. Open SAGA GIS and create a new project: File>Project>New Project
. 


 
