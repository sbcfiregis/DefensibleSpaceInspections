n/a. ~~inspectorf" to "preventi3" need to be blank.  address_lo check for blanks~~

n/a. ~~Clear out the following fields; inspectorp, occupant home, inspecti_1, any violations (A-M), escalate
  -Update report title in data as well as new year's app.~~

1. Find and replace all "Unable to Assess" with blank

2. Add/subtract based on newly approved SRA (every 5-years; 2021,2026,etc)

3. _Status Conversions_

  ~~- if missing any structure data= "Incomplete Data or Never Inspected" (pink)~~
  
  - if not destroyed or incomplete, and inspectiondate is older than 1 year--> "Due for Inspection" ~~2021~~
  
4. Test 1 record for import into Fulcrum.  Screenshot field matching and all errors

5. Reconcile any intermediate records that may have been created over winter or AB38-related

6. Seperate records into 2 shapefiles (9,999) and the rest due to 10,000 record import limit.


# 2021 Changes

- Change "Unable to Assess" to "Not Observed" for structure data (Per CalFire)

# 2022 Changes

  ## CALFIRE CHANGES
- Collector to FieldMaps

- Addition of 4 new Statuses
  - Compliant 6 months - 1 year
  - Last Inspected 1-2 Years
  -	Last Inspected 2-3 Years
  - Inspected over 3 Years Ago
  
  ## SBC CHANGES AND UPDATED WORKFLOW
1. Export 2021 DSP as geodatabase (rename with letter)

2. Import into ArcPro

3. Add/ Subtract records based on newly approved SRA (every 5-years, 2021,2026,etc) 

4. Status Conversions
	- If inspection_date is older than 1 year ---> "Due for Inspection"
		Select all records with status "Due for Inspection", 
			- find and replace all "Unable to Assess" with blank
			- all columns from "inspectorf" to "preventi3" "inspection_date" need to be blank (EXCEPT address_visible, )
			- all shifts to blank


6. Test 1 record for import into Fulcrum. Screenshot field matching and all errors

7. Seperate records into 2 shapefiles (9,999) and the rest due to 10,000 record import limit.
 ____________________________________________________________________________________________

- Auto-populate and set hidden "Shift" column (calculated by data event using julian calendar [on-status-change]) [NOT YET ACTIVE]

- Python script created to update status records for 6mo-1yr old, (will need to be manually-run in PyCharm every day at 0800 hours)

