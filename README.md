# Pennsylvania Election Shapefile
This shapefile was compiled and processed by members of the Voting Rights Data Institute. 
The Voting Rights Data Institute (VRDI) was a 2018 summer intensive sponsored by the Metric 
Geometry and Gerrymandering Group (MGGG) at Tufts and MIT, with major support from a Bose 
Research Grant at MIT and from the Jonathon M. Tisch College of Civic Life at Tufts.

## Sources
The raw, unprocessed voting tabulation districts (VTDs) were collected from the US Census Bureau website. 
The VTDs are from 2011. Election data was compiled at the precinct level by a private individual 
and was found to be within 1% of the official state-reported results at the county and state levels.

## Processing
The VRDI team used several preprocessing tools (all available in https://github.com/gerrymandr/Preprocessing) 
to prepare the output shapefile for analysis: 
* donut_removal.py was used to simplify the shapefile geometries ensuring that no units contained any other units within it.
* county_split.py was used to ensure that VTDs do not overlap with multiple counties 
* faster_proration_with_counties.py was used to prorate the Black/African American population from Census blocks to VTDs
* used roundoff from prorationtAndRoundoff.py to match districting plans to VTDs

## Metadata
Below is a brief description of each of the listed variables in the attribute table of the VTD shapefile:
- `STATEFP10`: State FIPS code
- `COUNTYFP10`: County FIPS code
- `VTDST10`: Voting tabulation district FIPS code
- `GEOID10`: 8-digit FIPS code
- `VTDI10`: 2010 Census voting district indicator
- `NAME10`: Voting tabulation district name
- `NAMELSAD10`: Translated statistical area description code
- `LSAD10`: 2010 Census legal/statistical area description code for voting district 
- `MTFCC10`: MAF/TIGER feature class code
- `FUNCSTAT10`: 2010 Census functional status
- `ALAND10`: Area land (square meters)
- `AWATER10`: Area water (square meters)
- `INTPTLAT10`: Latitude of internal point
- `INTPTLONG10`: Longitude of internal point
- `ATG12D`: Number of votes for 2012 Democratic attorney general candidate
- `ATG12R`: Number of votes for 2012 Republican attorney general candidate
- `F2014GOVD`: Number of votes for 2014 Democratic gubernatorial candidate
- `F2014GOVR`: Number of votes for 2014 Republican gubernatorial candidate
- `GOV10D`: Number of votes for 2010 Democratic gubernatorial candidate
- `GOV10R`: Number of votes for 2010 Republican gubernatorial candidate
- `PRES12D`: Number of votes for 2012 Democratic presidential candidate
- `PRES12O`: Number of votes for 2012 other party's presidential candidate
- `PRES12R`: Number of votes for 2012 Republican presidential candidate
- `SEN10D`: Number of votes for 2010 Democratic senate candidate
- `SEN10R`: Number of votes for 2010 Republican senate candidate
- `T16ATGD`: Number of votes for 2016 Democratic attorney general candidate
- `T16ATGR`: Number of votes for 2016 Republican attorney general candidate
- `T16PRESD`: Number of votes for 2016 Democratic Presidential candidate
- `T16PRESOTH`: Number of votes for 2016 other party's presidential candidate
- `T16PRESR`: Number of votes for 2016 Republican presidential candidate
- `T16SEND`: Number of votes for 2016 Democratic senate candidate
- `T16SENR`: Number of votes for 2016 Republican senate candidate
- `USS12D`: Number of votes for 2012 Democratic senate candidate
- `USS12R`: Number of votes for 2012 Republican senate candidate
- `2011_PLA_1`: Congressional district ID in 2011 enacted congressional map
- `GOV`: Congressional district ID in Governor’s counter-proposed plan
- `TS`: Congressional district ID in Turzai-Scarnati Plan
- `REMEDIAL_P`: Congressional district ID in 2018 enacted remedial plan
- `538CPCT_1`: Congressional district ID in 538’s compactness favoring plan
- `538DEM_PL`: Congressional district ID in 538’s Democratic favoring plan
- `538GOP_PL`: Congressional district ID in 538’s Republican favoring plan
- `8THGRADE_1`: Congressional district ID in Jon Kimmel’s eighth grade class’s second redistricting plan
- `HISP_POP`: 2010 Hispanic or Latino population
- `TOT_POP`: 2010 Total population
- `WHITE_POP`: 2010 White alone population
- `BLACK_POP`: 2010 Black/African American alone population
- `NATIVE_POP`: 2010 American Indian or Alaska Native alone population
- `ASIAN_POP`: 2010 Asian alone population

## Projection
The shapefile uses a WGS 84 geographic coordinate system.
