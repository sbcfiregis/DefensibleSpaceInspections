# SBC Dashboard (update weekly)
# Follow Steps 1-9 for both Internal & CALFIRE Data

1) Login to Fulcrum app at: https://web.fulcrumapp.com/users/sign_in
2) Click on the __"2020 Defensible Space Inspections"__ App
3) Click __"Exporter Export Data"__ in bottom left

___

__File Format__: ESRI Shapefile (.shp)

__Date Range__: [Default]

__Date Time Zone__: (GMT-08:00) Pacific Time (US & Canada)

Ensure Correct App is checked __(2020 Defensible Space Inspections)__

4) Click __"Next"__
![alt text](https://github.com/sbcfiregis/photos/blob/master/fulcrum_screenshot.JPG?raw=true)

---

6) Confirm the settings are correct and that there are approximately __14,000+ records__
7) Click __"Confirm"__ and wait for export to complete, this may take a few minutes (once finished, you will see a down-arrow to the right of the layer)
8) Click the __"down-arrow"__ to download the file
9) Navigate to your Downloads folder on windows File Explorer and unzip the file (it will be named like: *Fulcrum_Export_3b08c3bf-09e2-4d66-96fd-30f08f8ad8b4*)
10) Navigate inside unzipped file until you get to the shapefiles
11) Select parts of the shapefile that __DO NOT INCLUDE__ "photoid" or "2020_inspection" and add "_SBC" to all 4 parts of the shapefile
(ex: 2019_defensible_space_inspections_SBC)
12) Bring shapefile into ArcMap/QGIS, open attribute table, create new __Date__ field (Titled: "Date") and __field calculate__ "Date" field from the "Inspecti_1" field.  NOTE: you may receive a processing error, but click yes and the process will complete. 
13) Check to make sure Uninspected or stucture destroyed has dates*
14) __Delete__ the following fields:

    a) created by

    b) updated by 
    
    c) inspectorf 
    
    d) inspectorl

    e) prevention 
    
    f) preventi_1 
    
    g) preventi_2 
    
    h) preventi_3 
    
    i) gateCode 
    
    j) Comments
    
    k) photoid_ur  
    
> __Close out__ 

**__Steps 13.1-13.8 below are OPTIONAL__ and only necessary once a month
____________________________________________________________________________
13.1) Follow steps 1-12 for MTO Defensible Space Records.  Select all records.
    
13.2) Select only __SRA Properties!__
    
13.3) Select all __EXCEPT__ records with status= "Needs...", "Vacant", "Incomplete", "Prevention" then __field calculate__ those that have passed to "Compliant".  Fix non-compliants.  
    
13.4) In MTO layer, create new fields for; status, latitude, longitude, address_fu.  __Field calculator__ these.

13.5) Test one record in how it merges to "2020_defensible_space_inspections_CALFIRE".  If all looks correct, copy rest of layer.

13.6) Select where calfireuni, county, battalion are blank.  Then __Field calculate__: calfireuni=SBC, county=SBA, battalion=1

13.7) __Field calculate__ "Date" field from the "Inspection" field.  NOTE: you may receive a processing error, but click yes and the process will complete.
_____________________________________________________________________________
15) Back in windows File Explorer, select all parts of "2020_defensible_space_inspections_SBC" shapefile, Right click and send to compressed/zipped folder.  Then save this zipped folder at: "L:\GIS\Base Data\DSP\2020 DSP Program\SBC AGOL" > create new folder here with the date you exported (e.g. 20200630)
## ArcGIS Online
16) Login to AGOL account here: https://sbc-gis.maps.arcgis.com/home/signin.html
17) Click __"Content"__ and search for __Feature Layer__ named __"2020_defensible_space_inspections_SBC"__
18) Click __"Update Data"__ > __"Overwrite Entire Layer"__
19) Ensure that the zip file you are uploading is named __exactly the same__ as it appears on AGOL and that you select the zip file that you saved in step 14 above > __"Overwrite"__
20) Wait ~ 2 minutes for upload to complete
21) Lastly, change the __summary__ field of the feature layer to the date uploaded (e.g. 2020/06/04) __VERY IMPORTANT__
22) Search for __SBC 2020 Defensible Space Inspection Dashboard__ > __Edit Application__ > change _Current as of date_ to same as above.  Save changes.

# CALFIRE Data (update monthly)
1) Extract the zipfile from the steps 1-9 above, and copy to downloads folder.
2) Once extracted, change name to "2020_SBC_defensible_space_inspections_CALFIRE"
3) Bring the shapefile into ArcMap or QGIS. See steps 13.1 for adding in MTO Data.
4) Open attribute table and  __"Select by attributes"__ where
> __"status" NOT IN ('Incomplete Data or Never Inspected', 'Due for Inspection 2020')__
5) "Create layer from Selected Features".  Open this attribute table and select where __"Date" IS NULL__  (These will be "Destroyed or "Locked Gates", where inspection was attempted)
6) Field calculate date for these based on the date last updated in fulcrum. (should be less than 20 records)
7) Enable editing, Find and Replace where fields = "Unable to Assess".   Then, "Replace All" to blank.  Save edits and stop editing.
8) Make sure to only choose records up until the last day of the month.  (For CF records-sake) 
9) __"Select by attributes"__ where
> __"status" IN ( 'Structure Destroyed', 'Uninspected (Locked Gate)')__.  Field Calculate selected features' "Status" field to "Uninspected" 

![alt text](https://github.com/sbcfiregis/photos/blob/master/dsp.JPG?raw=true)

10) De-select all records and Export data to new shapefile (same name), close out of Arcmap, zip up.
11) Navigate to file in windows explorer and save the zipfile at "L:\GIS\Base Data\DSP\2020 DSP Program\CAL FIRE AGOL\xxdatexx".  Then, delete shapefile located here
12) Import to AGOL: ***MUST DISABLE SYNC IN SETTINGS IN ORDER TO OVERWRITE, THEN RE-ENABLE AFTER UPLOAD**
    - Overwrite data
    - Update dates
