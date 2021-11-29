## Chicago Vaccine Distribution Analysis

The analysis was performed in collaboration with [WBEZ](https://www.wbez.org/) and [The Brown Institute](https://brown.columbia.edu/)

The main objective of this analysis is to understand the availability of vaccines at a provider level in the most vulnerable community areas in Chicago Area.

The Protect Chicago website has provided a detailed pdf about the methodology used to determine [Chicago COVID-19 Community Vulnerability Index (CCVI)](https://www.chicago.gov/content/dam/city/sites/covid/reports/012521/Community_Vulnerability_Index_012521.pdf). The index was calculated using the Chicago Community Area Naming convention.

We use the [FOIA vaccine shipment information dataset](https://github.com/smarthxg/chicago-vaccine-inequity/blob/main/Brown_Institute_for_Media_Innovation_FOIA.xlsx) to capture the vaccine availability on a Provider Level. The dataset provides us with the Address and Postal Zip Codes of the providers. Still, it doesn’t offer us the associated Chicago Community Area Name, which is essential to map this data back to high vulnerability community areas.

To enable such a mapping, we have used a third-party [plugin](https://gsuite.google.com/u/1/marketplace/app/geocoding_by_smartmonkey/1033231575312) to first find each address’s geolocation (Lat-Long). The lat-long and address mapping can be found [here](https://github.com/smarthxg/chicago-vaccine-inequity/blob/main/doses_by_provider.csv).

We then used the Community Boundary GeoJSON dataset from the City of Chicago [data portal](https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Community-Areas-current-/cauq-8yn6) to map each provider’s Lat-Long to the Chicago community area names they belong to.

![](https://github.com/smarthxg/chicago-vaccine-inequity/blob/main/provider_viz.png)

The Graph above shows a mapping of each provider to the appropriate Community Area Name and gives an idea of the distribution of providers in general.

The dataset was aggregated by the community area name to find the total number of vaccines available (from a Supply Perspective) in each community area.

We then considered the Community Areas marked as highly vulnerable according to the CCVI score and reported the vaccine availability numbers on an aggregate and a per capita level.

The analysis can be found in this [here](https://github.com/smarthxg/chicago-vaccine-inequity/blob/main/Provider_Address_%2B_Lat_Long_%2B_Community_Mapping.ipynb).
