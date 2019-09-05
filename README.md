# Pennsylvania Election Shapefile
This shapefile was processed by MGGG staff and members of the Voting Rights Data Institute. 
The Voting Rights Data Institute (VRDI) was a 2018 summer intensive sponsored by the Metric 
Geometry and Gerrymandering Group (MGGG) at Tufts and MIT, with major support from a Bose 
Research Grant at MIT and from the Jonathon M. Tisch College of Civic Life at Tufts.

## Sources
The 2011 voting tabulation district (VTD) and 2010 census block shapefiles were obtained from the US Census Bureau’s [TIGER/Line Shapefiles](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html). Block level demographic data for the 2010 Decennial Census were retrieved using the [Census API](https://api.census.gov/data/2010/dec/sf1). Election data was compiled at the precinct level by a private individual 
and was found to be within 1% of the official state-reported results at the county and state levels. 

## Processing
Demographic data were aggregated from the census block level and precincts were assigned to districts using [MGGG's proration software](https://github.com/mggg/maup). Election data were also prorated onto VTDs from the original precinct shapefile using the `maup` package.

## Metadata
Below is a brief description of each of the listed variables in the attribute table of the VTD shapefile:
- `STATEFP10`: State FIPS code
- `COUNTYFP10`: County FIPS code
- `VTDST10`: Voting tabulation district FIPS code
- `GEOID10`: VTD FIPS code
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
- `TOTPOP`: Total population in 2010 Census
- `NH_WHITE`: White, non-hispanic, population in 2010 Census
- `NH_BLACK`: Black, non-hispanic, population in 2010 Census
- `NH_AMIN`: American Indian and Alaska Native, non-hispanic, population in 2010 Census
- `NH_ASIAN`: Asian, non-hispanic, population in 2010 Census
- `NH_NHPI`: Native Hawaiian and Pacific Islander, non-hispanic, population in 2010 Census
- `NH_OTHER`: Other race, non-hispanic, population in 2010 Census
- `NH_2MORE`: Two or more races, non-hispanic, population in 2010 Census
- `HISP`: Hispanic population in 2010 Census
- `H_WHITE`: White, hispanic, population in 2010 Census
- `H_BLACK`: Black, hispanic, population in 2010 Census
- `H_AMIN`: American Indian and Alaska Native, hispanic, population in 2010 Census
- `H_ASIAN`: Asian, hispanic, population in 2010 Census
- `H_NHPI`: Native Hawaiian and Pacific Islander, hispanic, population in 2010 Census
- `H_OTHER`: Other race, hispanic, population in 2010 Census
- `H_2MORE`: Two or more races, hispanic, population in 2010 Census
- `VAP`: Total voting age population in 2010 Census
- `HVAP`: Hispanic voting age population in 2010 Census
- `WVAP`: White, non-hispanic, voting age population in 2010 Census
- `BVAP`: Black, non-hispanic, voting age population in 2010 Census
- `AMINVAP`: American Indian and Alaska Native, non-hispanic, voting age population in 2010 Census
- `ASIANVAP`: Asian, non-hispanic, voting age population in 2010 Census
- `NHPIVAP`: Native Hawaiian and Pacific Islander, non-hispanic, voting age population in 2010 Census
- `OTHERVAP`: Other race, non-hispanic, voting age population in 2010 Census
- `2MOREVAP`: Two or more races, non-hispanic, voting age population in 2010 Census
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
- `REMEDIAL`: Congressional district ID in 2018 enacted remedial plan
- `GOV`: Congressional district ID in Governor’s counter-proposed plan
- `TS`: Congressional district ID in Turzai-Scarnati Plan
- `CD_2011`: Congressional district ID in 2011 enacted congressional map
- `SEND`: State Senate district ID
- `HDIST`: State House district ID
- `538DEM`: FiveThirtyEight Democratic favoring plan
- `538GOP`: FiveThirtyEight GOP favoring plan
- `538CMPCT`: FiveThirtyEight plan favoring compactness

## Projection
The shapefile uses a WGS 84 geographic coordinate system.

## Rating
We give this shapefile a C rating as election results were compiled by a private individual rather than by ourselves or the Secretary of State's offce. While election results were verified at the state and county levels, we acknowledge the possibility of error at the sub-county level.
