# Pennsylvania Election Shapefile
This shapefile was processed by MGGG staff and members of the Voting Rights Data Institute. 
The Voting Rights Data Institute (VRDI) was a 2018 summer intensive sponsored by the Metric 
Geometry and Gerrymandering Group (MGGG) at Tufts and MIT, with major support from a Bose 
Research Grant at MIT and from the Jonathan M. Tisch College of Civic Life at Tufts.

## Sources
The 2011 voting tabulation district (VTD) and 2010 census block shapefiles were obtained from the US Census Bureau’s [TIGER/Line Shapefiles](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html). Block level demographic data for the 2010 Decennial Census were retrieved using the [Census API](https://api.census.gov/data/2010/dec/sf1). Election data was compiled at the precinct level by a private individual. 

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
- `GOV14D`: Number of votes for 2014 Democratic gubernatorial candidate
- `GOV14R`: Number of votes for 2014 Republican gubernatorial candidate
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
The shapefile uses a UTM Zone 18N projection (EPSG: 26918).

## Rating
We give this shapefile a C rating as election results were compiled by a private individual rather than by ourselves or the Secretary of State's offce. While election results were verified at the state and county levels, we acknowledge the possibility of error at the sub-county level.

## Some notes on contiguity
VTDs in this shapefile come with district assignments for several plans relevant to the 2018 State Supreme Court case. It is important to note that because most of the plans were drawn using census blocks, there are places where the legal plans cut through the units of this shapefile. VTDs were assigned to the district that contains the majority of its area. In places this creates noncontiguous districts which can cause errors when trying to use the plan as an initial partition for [GerryChain](https://github.com/mggg/GerryChain). We suggest using the function `recursive_tree_part` to create a seed plan as a starting point. If it is important to use one of the plans provided as a starting point for chain, adding edges on your dual graph between nodes (7648,7635) and (1247,1160) should fix connectivity problems for `CD_2011` and `GOV`. The `538DEM` and `538CMPCT` plans have some VTDs that look to be incorrectly assigned in the shapefiles provided on FiveThirtyEight's [Atlas of Redistricting repository](https://github.com/fivethirtyeight/redistricting-atlas-data). We have chosen to follow their assignments, but would suggest reassigning `GEOID10` = '420033150' to district '12' to make the `538DEM` plan contiguous and reassigning '42061430' to district '09' and '4210380' and '4210370' to district '17' to make the `538CMPCT` plan contiguous. For more information, please refer to this GerryChain [documentation](https://gerrychain.readthedocs.io/en/latest/user/islands.html#discontiguous-plans).

## Addendums
2014 and 2020 elections were added to this dataset as a new beta version shapefile in October 2021, compiled and processed by MGGG lab members. These elections were sourced from the the Pennsylvania Secertary of State Office and were joined to the pre-existing 2016-2018 election results on 2020 vtd shapes. This shapefile maintains the C rating due to the difficulties in the joining process. The shapefile holds a 99.5% vote count accuracy. 

Definitions for the columns novel to this version are listed below: 
AG20D- Votes for Democratic Attorney General candidate 2020 (Josh Shapiro)
AG20R- Votes for Republican Attorney General candidate 2020 (Heather Heidelbaugh)
AUD20D- Votes for Democratic Auditor candidate 2020 (Nina Ahmad)
AUD20R- Votes for Republican Auditor candidate 2020 (Timothy DeFoor)
TRES20D- Votes for Democratic Treasurer candidate 2020 (Joe Torsella)
TRES20R- Votes for Republican Treasurer candidate 2020 (Stacy Garrity)
PRES20D- Votes for Democratic Presidential candidate 2020 (Joe Biden)
PRES20R- Votes for Republican Presidential candidate 2020 (Donald Trump)
GOV14D- Votes for Democratic Gubernatorial candidate 2014 (Tom Wolf)
GOV14R- Votes for Republican Gubernatorial candidate 2014 (Tom Corbett)
