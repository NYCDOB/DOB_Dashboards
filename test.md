## DOB Building Profiles

The DOB Building Profiles application provides users with a near real-time view into construction and building code enforcement activities from both a citywide and a building-level perspective. The total number of construction permits issued, complaints generated, inspections conducted, violations issued, and construction-related accidents is aggregated at the building-level on a rolling 12-month period. This information gives the user a view into construction industry and DOB compliance activities throughout the five boroughs. 

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

*	Building Information System
    + Permits
    + Complaints
    + Violations
*	DOB NOW Build Permits
*	DOB NOW Inspections
*	DOB Incident Database
*	NYC Building Footprints

## Data Definitions
### Main Menu (12 month metrics)
| Metric | Definition |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| All Buildings | Every building that has interacted with the DOB  via permit, complaints, inspection, violations, and accidents |
| Total Permits | Every building where a DOB permit was issued |
| BIS Permits | Every building where a DOB permit was issued in person through one of our Borough Offices, through the Development Hub, or online through e-Filing |
| DOB NOW Permits | Every building where a DOB permit was issued through DOB NOW: Build |
| New Buildings | Every building where a permit was issued to build an entirely new building |
| Total Complaints | Every building where a complaint was issued to the DOB |
| Illegal Conversion | An illegal conversion is an alteration or modification of an existing building to create an additional housing unit without first obtaining approval from the New York City DOB Every building where the DOB received a complaint about illegal conversion |
| Work Without Permit | Every building where the DOB received a complaint about construction occurring without an active DOB permit |
| Tenant Harassment | Every building where the DOB received a complaint about tenant harassment |
| Total Inspections | Every building where the DOB performed  an inspection |
| Build it Back | Every building where the DOB performed an inspection  on construction work that was done in response to Hurricane Sandy |
| Boilers | Every building where the DOB performed an inspection  on a high or low pressure water boiler |
| Building Marshal | Every building where the DOB performed an inspection  on ... |
| Construction (DEV) | Every building where the DOB performed an inspection  on permitted construction work |
| Construction (ENF) | Every building where the DOB performed an inspection  to confirm that the building is complying with all applicable laws and building code |
| Cranes | Every building where the DOB performed an inspection  on permitted construction cranes |
| Electrical (DEV) | Every building where the DOB performed an inspection  on permitted electrical work |
| Electrical (ENF) | Every building where the DOB performed an inspection  to confirm that the building is complying with all applicable laws and building code for electrical work |
| Elevators | Every building where the DOB  performed an inspection  on the elevators in the building |
| Emergency Response | Every building where the DOB performed an inspection  in response to an emergency |
| Facades | Every building where the DOB  performed an inspection  on the building façade |
| Plumbing (DEV) | Every building where the DOB performed an inspection  on permitted plumbing work |
| Plumbing (ENF) | Every building where the DOB performed an inspection  to confirm that the building is complying with all applicable laws and building code for plumbing work |
| Quality of Life | Every building where the DOB performed an inspection  that impacts the quality of life of residents of the building |
| Sustainability | Every building where the DOB performed an inspection  to confirm that the building is complying with all applicable laws and building code that impact sustainability and energy use |
| Total Violations | Every building where the DOB issued a DOB Violation or an ECB Violation (OATH Summons) |
| ECB Violations | Every building where the DOB issued an ECB Violation (OATH Summons) |
| Stop Work Orders | Every building where the DOB ordered construction professionals to stop work immediately |
| Vacate Orders | Every building where the DOB ordered everyone to vacate the building |
| Construction Accidents | Every building where an injury or fatality occurred as a result of construction work |
| Worker Fell | Every building where a construction worker fell on a worksite |
| Material Failure | Every building where a collapse occurred due to material failure |
| Mechanical Equipment | Every building where mechanical equipment caused an accident on a worksite |

### Profile Info

| Metric | Definition |
|-------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Borough | Indicates which of the 5 NYC boroughs the building is located in |
| Year Built | Indicates the year that the building was built (NYC Building Footprints) |
| BIN Profile | Provides a link to the building’s profile page on Building Information System (BIS), where you can find more detail about every transaction that the building has with the Department of Buildings |
| Cyclomedia Street View | A photo of the building taken from the street by Cyclomedia. This may or may not show active construction work that corresponds with what is reported in the data |
| 12-month building statistics: | This section shows the count of all permits, complaints, inspections, violations, and accidents in the past 12 months from today that correspond to this building |


## Built by

* DOB Analytics and Data Science Team

## Acknowledgments

* Something here

