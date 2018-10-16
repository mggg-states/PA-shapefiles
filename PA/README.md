# Pennsylvania Election Shapefile
This shapefile was compiled and processed by members of the Voting Rights Data Institute. 
The Voting Rights Data Institute (VRDI) was a 2018 summer intensive sponsored by the Metric 
Geometry and Gerrymandering Group (MGGG) at Tufts and MIT, with major support from a Bose 
Research Grant at MIT and from the Jonathon M. Tisch College of Civic Life at Tufts.

The raw, unprocessed voting tabulation districts (VTDs) were collected from the US Census Bureau website. 
The VTDs are from 2011. Election data was compiled at the precinct level by a private individual 
and was found to be within 1% of the official state-reported results at the county and state levels.

The VRDI team used several preprocessing tools (all available in https://github.com/gerrymandr/Preprocessing) 
to prepare the output shapefile for analysis: 
* donut_removal.py was used to simplify the shapefile geometries ensuring that no units contained any other units within it.
* county_split.py was used to ensure that VTDs do not overlap with multiple counties 
* faster_proration_with_counties.py was used to prorate the Black/African American population from Census blocks to VTDs
* used roundoff from prorationtAndRoundoff.py to match districting plans to VTDs

The shapefile uses a WGS 84 geographic coordinate system.

