1. "inspectorf" to "preventi3" need to be blank.  address_lo check for blanks

~~2. Clear out the following fields; inspectorp, occupant home, inspecti_1, any violations (A-M), escalate
  -Update report title in data as well as new year's app. ~~

3. Find and replace all "Unable to Assess" with blank

4. Add/subtract based on newly approved SRA (every 5-years; 2021,2026,etc)

5. _Status Conversions_

  - if missing any structure data= "Incomplete Data or Never Inspected" (pink)
  
  - if not destroyed or incomplete= "Due for Inspection ~~2021~~
  
6. Test 1 record for import into Fulcrum.  Screenshot field matching and all errors

7. Seperate records into 2 shapefiles (9,999) and the rest due to 10,000 record import limit.


# 2021 Changes

- Change "Unable to Assess" to "Not Observed" for structure data (Per CalFire)

# 2022 Changes

CALFIRE CHANGES
- Collector to FieldMaps

- Addition of 4 new Statuses
  - Compliant 6 months - 1 year
  - Last Inspected 1-2 Years
  -	Last Inspected 2-3 Years
  - Inspected over 3 Years Ago
  
SBC CHANGES

- Auto-populate and set hidden "Shift" column (calculated by data event using julian calendar [on-status-change])

- Python script created to update status records for 6mo-1yr old, (runs every day at 2200 hours)

