# Steps 1-12 for Internal Data

1) Login to Fulcrum app at: https://web.fulcrumapp.com/users/sign_in
2) Click on the __"Defensible Space Inspections"__ App
3) Click __"Exporter Export Data"__ in bottom left

___

__File Format__: ESRI Shapefile (.shp)

__Date Range__: [Default]

__Date Time Zone__: (GMT-08:00) Pacific Time (US & Canada)

Ensure Correct App is checked __(2018 Defensible Space Inspections)__

4) Click "Next"
![alt text](https://github.com/sbcfiregis/photos/blob/master/fulcrum_screenshot.JPG?raw=true)

---

6) Confirm the settings are correct and that there are approximately __15,000+ records__
7) Click __"Finish"__ and wait for export to complete (once finished, you will see a down-arrow to the right of the layer)
8) Click the __"down-arrow"__ to download the file
9) Navigate to your Downloads folder on windows File Explorer and unzip the file (it will be name like: Fulcrum_Export_3b08c3bf-09e2-4d66-96fd-30f08f8ad8b4)
10) Navigate inside unzipped file until you get to the shapefiles
11) Select all parts of the shapefile that __DO NOT INCLUDE__ "photoid"
12) Right click and send to compressed/zipped folder
## ArcGIS Online
13) Login to AGOL account here: https://sbc-gis.maps.arcgis.com/home/signin.html
14) Click __"Content"__ and search for __Feature Layer__ named __"2018_defensible_space_inspections_SBC"__
15) Click __"Update Data" > "Append Data to Layer"
16) Ensure that the zip file you are uploading is named __exactly the same__ as it appears on AGOL
17) Once upload has completed, ensure __"Update existing features" is checked and __"FID matches to FID"__
18) Click __"Apply"
19) Lastly, change the __summary__ field of the feature layer to the date upload (e.g. 2018/12/04)
