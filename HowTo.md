# Follow Steps 1-9 for both Internal & CALFIRE Data

1) Login to Fulcrum app at: https://web.fulcrumapp.com/users/sign_in
2) Click on the __"2019 Defensible Space Inspections"__ App
3) Click __"Exporter Export Data"__ in bottom left

___

__File Format__: ESRI Shapefile (.shp)

__Date Range__: [Default]

__Date Time Zone__: (GMT-08:00) Pacific Time (US & Canada)

Ensure Correct App is checked __(2019 Defensible Space Inspections)__

4) Click __"Next"__
![alt text](https://github.com/sbcfiregis/photos/blob/master/fulcrum_screenshot.JPG?raw=true)

---

6) Confirm the settings are correct and that there are approximately __15,000+ records__
7) Click __"Finish"__ and wait for export to complete, this may take a few minutes (once finished, you will see a down-arrow to the right of the layer)
8) Click the __"down-arrow"__ to download the file
9) Navigate to your Downloads folder on windows File Explorer and unzip the file (it will be named like: *Fulcrum_Export_3b08c3bf-09e2-4d66-96fd-30f08f8ad8b4*)
10) Navigate inside unzipped file until you get to the shapefiles
11) Select parts of the shapefile that __DO NOT INCLUDE__ "photoid" or "2019_inspection" and add "_SBC" to all 4 parts of the shapefile
(ex: 2019_defensible_space_inspections_SBC)
12) Bring shapefile into ArcMap/QGIS, open attribute table, create new __Date__ field and __field calculate__ "Date" field from the "Inspection" field.  NOTE: you may receive a processing error, but click yes and the process will complete.  
13) Delete the following fields: created by, updated by, engine_co, engine_co1, prevention, preventi_1, preventi_2, preventi_3, gateCode, Comments, photoid_ur,  > __Close out__  
13) Follow steps 1-12 for MTO Defensible Space Records.  Select only records with structure and vegetation assessments complete.
    __"All Inspections Current", "1st Non Compliant", "2nd Compliant", "2nd Non Compliant", "3rd Compliant", "4th Non Compliant-Citation"__
13b) Select only __SRA Properties!__
13c) Merge MTO data to SBC ------
14) Back in windows File Explorer, select all parts of SBC shapefile, Right click and send to compressed/zipped folder
## ArcGIS Online
15) Login to AGOL account here: https://sbc-gis.maps.arcgis.com/home/signin.html
16) Click __"Content"__ and search for __Feature Layer__ named __"2019_defensible_space_inspections_SBC"__
17) Click __"Update Data"__ > __"Overwrite Entire Layer"__
18) Ensure that the zip file you are uploading is named __exactly the same__ as it appears on AGOL and that you select the zip file __within__ the downloaded folder > __"Overwrite"__
19) Wait ~ 2 minutes for upload to complete
20) Lastly, change the __summary__ field of the feature layer to the date uploaded (e.g. 2018/12/04) __VERY IMPORTANT__
21) Search for __SBC 2019 Defensible Space Inspection Dashboard__ > __Edit Application__ > change _Current as of date_ to same as above.  Save changes.

# CALFIRE Data
1) Use the unzipped file from following steps 1-9 above
2) Bring the shapefile into ArcMap or QGIS
3) Open attribute table and  __"Select by attributes"__ where
> __"status" IN ('Incomplete Data or Never Inspected', 'Due for 2019 Inspection', 'Not Inspected Since 2017', 'Structure Destroyed', 'Uninspected (Locked Gate)')__

![alt text](https://github.com/sbcfiregis/photos/blob/master/2019_Fulcrum_DSP_Status_screenshot.PNG?raw=true)

4) Click __"Show Selected Records"__ button below attribute table
5) Right-click on _status_ in attribute table and __Field Calculator__
6) Input __"Uninspected"__
7) Click __"OK"__ to run the field calculation
8) "Clear Selected Features"
9) Right-click on layer in __Layers__ and select __"Data"__>__"Export Data"__
10) Save layer at L:/GIS/Base Data/DSP/2019 DSP Program/CAL FIRE AGOL/ > create a new folder with date as "20190708" > Save as a shapefile and named: __"2019_SBC_defensible_space_inspections_CALFIRE"__
11) Once layer finishes saving, find in windows explorer and zip the shapefile.
12) Import to AGOL by following steps 13-19 above 
(except search for and update __"2019_SBC_defensible_space_inspections_CALFIRE"__)
