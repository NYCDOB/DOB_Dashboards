## DOB Building Profiles

The New York City Department of Buildings (DOB) Building Profiles application provides near real-time insight into construction and building code enforcement activities from both a citywide and a building-level perspective. The total number of construction permits issued, complaints generated, inspections conducted, violations issued, and construction-related accidents is aggregated at the building-level on a rolling 12-month period. This information gives the user a view into construction industry and DOB compliance activities throughout the five boroughs. 

![Alt Text](https://github.com/NYCDOB/DOB_Dashboards/blob/Dev_2016/profiles_screen.PNG)

## Built With

* [R](https://www.r-project.org/)
    + Core packages(dplyr, tidyr, RJDBC, ...)
* [Carto VL](https://carto.com/developers/carto-vl/)
* [Mapbox GL](https://www.mapbox.com/mapbox-gl-js/api/)
* [D3](https://d3js.org/)
* [Bootstrap](https://getbootstrap.com/)

## Backend Processes  

Data are extracted using R-JDBC connection protocol to OBIEE. Logical SQL is issued against tables of the OBIEE semantic layer.  Data extractions from multiple databases are cleaned, filtered, and aggregated at the building (BIN) level, merged with the NYC Building Footprints, then pushed out to Carto via automated ETL processes. 

## Data Sources

*	[Building Information System](http://a810-bisweb.nyc.gov/bisweb/bsqpm01.jsp)
    + Permits
    + Complaints
    + Violations
*	DOB NOW Build Permits
*	DOB NOW Inspections
*	DOB Incident Database
*	[NYC Building Footprints](https://github.com/CityOfNewYork/nyc-geo-metadata/blob/master/Metadata/Metadata_BuildingFootprints.md)

## Data Definitions
### Main Menu (12 month metrics)
| Metric | Definition |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| All Buildings | Every building that has interacted with DOB via permit, complaints, inspection, violations, and accidents |
| Total Permits | Every building where a DOB permit was issued |
| BIS Permits | Every building where a DOB permit was issued in person through one of our [Borough Offices](https://www1.nyc.gov/site/buildings/about/borough-offices.page), through the [Development Hub](https://www1.nyc.gov/site/buildings/business/development-hub.page), or online through [e-Filing](https://a810-efiling.nyc.gov/eRenewal/loginER.jsp) |
| DOB NOW Permits | Every building where a DOB permit was issued through [DOB NOW: Build](https://www1.nyc.gov/site/buildings/industry/dob-now-build.page) |
| New Buildings | Every building where a permit was issued to build an entirely new building |
| Total Complaints | Every building where a complaint was issued to DOB |
| Illegal Conversion | Every building where DOB received a complaint about [illegal conversion](https://www1.nyc.gov/site/buildings/renter/illegal-conversions-vacates.page)<br><br>`This is the first definition I have noted for adding code.` I suggest this simple syntax because I had trouble getting [fenced syntax](https://docs.gitlab.com/ee/user/markdown.html#code-and-syntax-highlighting) to work within a table|
| Work Without Permit | Every building where DOB received a complaint about construction occurring without an active DOB permit<br><br>`Need code here too. Even if it's as simple as "Use Complaint Categories 5, 58, 66, and 1J"` |
| Tenant Harassment | Every building where DOB received a complaint about [tenant harassment](https://www1.nyc.gov/site/buildings/renter/tenant-harrassment.page)<br><br>`Need code here` |
| Total Inspections | Every building where DOB performed an inspection |
| Build it Back | Every building where DOB performed an inspection on construction work that was done in response to [Hurricane Sandy](https://www1.nyc.gov/site/buildings/homeowner/storm-update.page) |
| Boilers | Every building where DOB performed an inspection on a high or low pressure water boiler |
| Building Marshal | Every building where the [Office of the Buildings Marshal](https://www1.nyc.gov/site/buildings/about/agency-units.page#obm) performed an inspection |
| Construction (DEV) | Every building where DOB performed an inspection on permitted construction work |
| Construction (ENF) | Every building where DOB performed an inspection to confirm that the building is complying with all applicable laws and building code |
| Cranes | Every building where DOB performed an inspection on construction cranes |
| Electrical (DEV) | Every building where DOB performed an inspection on permitted electrical work |
| Electrical (ENF) | Every building where DOB performed an inspection to confirm that the building is complying with all applicable laws and building code for electrical work |
| Elevators | Every building where DOB performed an inspection on the elevators in the building |
| Emergency Response | Every building where DOB performed an inspection in [response to an emergency](https://www1.nyc.gov/site/buildings/about/agency-units.page#ert) |
| Facades | Every building where DOB performed an inspection on the [building façade](https://www1.nyc.gov/site/buildings/safety/facades.page) |
| Plumbing (DEV) | Every building where DOB performed an inspection on permitted plumbing work |
| Plumbing (ENF) | Every building where DOB performed an inspection to confirm that the building is complying with all applicable laws and building code for plumbing work |
| Quality of Life | Every building where DOB performed an inspection that impacts the [quality of life](https://www1.nyc.gov/site/buildings/renter/quality-of-life-unit.page) of residents of the building |
| Sustainability | Every building where DOB performed an inspection to confirm that the building is complying with all applicable laws and building code that impact [sustainability](https://www1.nyc.gov/site/buildings/industry/sustainability.page) and energy use |
| Total Violations | Every building where DOB issued a [DOB Violation or an ECB Violation](https://www1.nyc.gov/site/buildings/homeowner/violations-vacates.page) (OATH Summons) |
| ECB Violations | Every building where DOB issued an ECB Violation (OATH Summons) |
| Stop Work Orders | Every building where DOB ordered construction professionals to [stop work immediately](https://www1.nyc.gov/site/buildings/homeowner/stop-work-orders.page)<br><br>`Need code here` |
| Vacate Orders | Every building where DOB ordered everyone to [vacate the building](https://www1.nyc.gov/site/buildings/homeowner/violations-vacates.page)<br><br>`Need code here` |
| Construction Accidents | Every building where an injury or fatality occurred as a result of construction work |
| Worker Fell | Every building where a construction worker fell on a worksite |
| Material Failure | Every building where a collapse occurred due to material failure |
| Mechanical Equipment | Every building where mechanical equipment caused an accident on a worksite |

### Profile Info

| Metric | Definition |
|-------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Borough | Indicates which of the 5 NYC boroughs the building is located in |
| Year Built | Indicates the year that the building was built (source: NYC Building Footprints) |
| BIN Profile | Provides a link to the building’s profile page on Building Information System (BIS), where you can find more detail about every transaction that the building has with DOB |
| Cyclomedia Street View | A photo of the building taken from the street by [Cyclomedia](https://www.cyclomedia.com/us). This may or may not show active construction work that corresponds with what is reported in the data |
| 12-month building statistics | This section shows the count of all permits, complaints, inspections, violations, and accidents in the past 12 months from today that correspond to this building |


## Built by

* [DOB Analytics and Data Science Team](https://www1.nyc.gov/site/buildings/about/metrics-reports.page) - If you have questions or feedback, comment here on github or email us at [Analytics@buildings.nyc.gov](mailto:analytics@buildings.nyc.gov). (Note: We're hiring a web developer!)

## Acknowledgments

* Inspired by [NYC Planning Labs](https://planninglabs.nyc/)

