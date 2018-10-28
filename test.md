## DOB Building Profiles

The DOB Building Profiles application provides users with a near real-time view into construction and building code enforcement activities from both a citywide and a building-level perspective. The total number of construction permits issued, complaints generated, inspections conducted, violations issued, and construction-related accidents is aggregated at the building-level on a rolling 12-month period. This information gives the user a view into construction industry and DOB compliance activities throughout the five boroughs. 

## Built With

* [R](https://www.r-project.org/)
* [Carto VL](https://carto.com/developers/carto-vl/)
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

## Authors

* **DOB Analytics and Data Science Unit** 

## Acknowledgments

* Something here

