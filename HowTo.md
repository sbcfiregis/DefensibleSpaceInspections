# Follow Steps 1-9 for both Internal & CALFIRE Data

1) Login to Fulcrum app at: https://web.fulcrumapp.com/users/sign_in
2) Click on the __"Defensible Space Inspections"__ App
3) Click __"Exporter Export Data"__ in bottom left

___

__File Format__: ESRI Shapefile (.shp)

__Date Range__: [Default]

__Date Time Zone__: (GMT-08:00) Pacific Time (US & Canada)

Ensure Correct App is checked __(2018 Defensible Space Inspections)__

4) Click __"Next"__
![alt text](https://github.com/sbcfiregis/photos/blob/master/fulcrum_screenshot.JPG?raw=true)

---

6) Confirm the settings are correct and that there are approximately __15,000+ records__
7) Click __"Finish"__ and wait for export to complete, this may take a few minutes (once finished, you will see a down-arrow to the right of the layer)
8) Click the __"down-arrow"__ to download the file
9) Navigate to your Downloads folder on windows File Explorer and unzip the file (it will be named like: *Fulcrum_Export_3b08c3bf-09e2-4d66-96fd-30f08f8ad8b4*)
10) Navigate inside unzipped file until you get to the shapefiles
11) Select all parts of the shapefile that __DO NOT INCLUDE__ "photoid" and add "_SBC" to all 4 parts of the shapefile
(ex: 2019_defensible_space_inspections_SBC)
12) Bring shapefile into ArcMap/QGIS and __field calculate__ "Date" field from the "Inspection" field.  Close out.  
13) Follow steps 1-12 for MTO Defensible Space Records.  Select only records with structure and dvegetation assessments complete.
15) Back in windows File Explorer, Right click and send to compressed/zipped folder
## ArcGIS Online
16) Login to AGOL account here: https://sbc-gis.maps.arcgis.com/home/signin.html
17) Click __"Content"__ and search for __Shapefile__ named __"2019_defensible_space_inspections_SBC"__
18) Click __"Update"__ > "Update Item"
19) Ensure that the zip file you are uploading is named __exactly the same__ as it appears on AGOL and that you select the zip file __within__ the downloaded folder
20) Once upload has completed, ensure __"Update existing features"__ is checked and __"FID matches to FID"__
21) Click __"Apply Updates"__
22) Lastly, change the __summary__ field of the feature layer to the date uploaded (e.g. 2018/12/04) __VERY IMPORTANT__
23) Repeat steps #15-19 for the feature layer of the same name.

# CALFIRE Data
1) Use the unzipped file from following steps 1-9 above
2) Bring the shapefile into ArcMap or QGIS
3) Open attribute table and  __"Select by attributes"__ where
> __status='Not Started (Never Inspected)' OR status='Uninspected (Locked Gate)'__

![alt text](https://github.com/sbcfiregis/photos/blob/master/status.JPG?raw=true)

4) Click __"Show Selected Records"__ button below attribute table
5) Right-click on _status_ in attribute table and __Field Calculator__
6) Input __"Not Started"__
7) Click __"OK"__ to run the field calculation
8) Once calculation is complete, Clear selected features, then __"Select by attributes"__ where
> __status='Uninspected (Not in 2018)'__
9) Click __"Show Selected Records"__ below atrribute table
10) Right-click on _status_ in attribute table and __Field Calculator__
11) Input __"Uninspected"__
12) Once calculation is complte, Clear Selected features.
13) Right-click on layer in __Layers__ and select __"Data"__>__"Export Data"__
14) Save the layer as a shapefile and named: __"2018_SBC_defensible_space_inspections_CALFIRE"__
15) Once layer finishes saving, find in windows explorer and zip the shapefile.
16) Import to AGOL by following steps 13-19 above 
(except search for and update __"2018_SBC_defensible_space_inspections_CALFIRE"__)
