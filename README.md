# Analyzing NYPD parking complaints in 77 NYC police precincts
This is a project about illegal parking complaints filed nearby police precincts in NYC.
 
*Read the story here: [Enforcer, or Offender?](https://xinyitu.github.io/precinct-parking/)*
## Goal
Over the years, a few Twitter accounts that document police parking violations have filed thousands of 311 complaints regarding this issue. However, since 311 parking complaints are handled by the NYPD itself, officers who parked their cars illegally near precincts were rarely punished for their actions. I want to look at the this systemic issue through a data-driven perspective and track how each precinct handle parking violations happened near their precinct.

## Data Collection
- 311 data is retrieved from [NYC Open Data](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9). Each row in this dataset is one 311 complaint, including its location, type of violation, open and close date and time, etc.
- Precinct addresses are scraped from the NYPD's [website](http://wgetsnaps.github.io/nyc.gov--nypd-videos/html/nypd/html/home/precincts.shtml). 

## Methodlogy & Analysis
#### Challenge:
311 data does not specify the kind of vehicle (whether it's a police vehicle or not). Therefore, I decide to look at all complaints that happened within one block distance of every police precinct. 
#### Steps
1. Get precinct's geo-location data through Google Maps API.
2. Filter 311 data to include only 311 complaints about "parking violation" with descriptor "blocked sidewalk", from March 2016 to March 2023.
5. In QGIS, calculate the distance between each 311 complaints to it nearest precinct, then filtered to include only complaints within 100-meter radius (roughly one block distance) of precincts.
6. Export this data from QGIS and analyze averge closing time, complaint response, etc. in Python notebook.

note: Google StreetView is used to cross-check whether violations happened around these precincts.

## Findings
- About 7 precincts have a high amount of parking complaints around its precinct compared to the rest:![Screen Shot 2023-04-09 at 3 52 01 PM](https://user-images.githubusercontent.com/116761432/230793713-0c7d7b66-d48d-4c86-9a54-d202890b0d57.png)
- Some precincts close these complaints in an extreme short period of time—a sign that these coomplaints were dismissed without proper investigation.
- Parking violations around precincts were rarely fined—most of these complaints were dismissed. 
For instance, this is the 76th police precinct, which has the highest amount of parking complaints. The median closing time of complaints is 7 minutes, and most cases werr closed with the response "police action not necessary."
![Screen Shot 2023-04-09 at 3 55 28 PM](https://user-images.githubusercontent.com/116761432/230793852-122dc2bb-1299-4ed5-bf38-b69c4ef8cdcd.png)


## Tools used
- QGIS
- Google Maps API
- Mapbox Studio
- Adobe Illstrator
- ai2html


## Challenges and possible improvement
- It is impossible that some complaints were filed against vehicles that do not belong to police officers. 
- Police vehicles parked outside the block where precincts are located weren't accounted for in this analysis.

## Contact
I can be reached at xt2274@columbia.edu or on Twitter @CynthiaTu2. Inbox is open for comments and suggestions. 

Check out my portfolio [here](https://xinyitu.github.io/)!

