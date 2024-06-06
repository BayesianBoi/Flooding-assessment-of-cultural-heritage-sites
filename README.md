# Cultural Heritage Sites at Risk of Flooding in Copenhagen
This project uses a simple height model to assess the risk of flooding on cultural heritage sites in Copenhagen.

## Repository structure
- `/src`: Contains all scripts for preprocessing, analysis and plotting.
- `/in/raw_data`: Contains all raw data files.
- `/out`: Contains outputs such as the leaflet map.

## Interactive map
Explore the interactive map to see the cultural heritage sites and their risk levels based on different water level scenarios by downloading the [Leaflet plot](https://github.com/BayesianBoi/Flooding-assessment-of-cultural-heritage-sites/blob/main/out/leaflet_map.html) and opening it it in any browser.

## Data sources
The necessary data, except for the Danish Hydrologic Height Model (DHHM) and the cultural heritage site data, are available in the `/in/raw_data` folder. Before running the analysis, download the DHHM and the cultural heritage site data, and place them in the `/in/raw_data` folder.

- **Cultural Heritage Sites (anlægsdata)**: [Kulturarv.dk](https://www.kulturarv.dk/fundogfortidsminder/Download/)
- **Municipality Data**: [GADM](https://gadm.org/data.html)
- **Postal Code Data**: [DAWA API](https://dawadocs.dataforsyningen.dk/dok/api/postnummer#)
- **Danish Hydrologic Height Model**: [Dataforsyningen](https://dataforsyningen.dk/data/2695)

*Note: The DHM data is available in grids of 10x10 km. Ensure you download the grids that encompass the area of Copenhagen.*

## Scripts
## Preprocessing
The preprocessing script prepares the cultural heritage and municipality data for analysis. It does the following:

- Loading cultural heritage sites from `anlægsdata`
- Loading municipality data from GADM
- Loading postal code data from the DAWA portal
- Filtering and transforming the data to focus on Copenhagen

## Analysis
The analysis script processes the preprocessed data to assess flood risks. It does the following:

- Loading the Danish Hydrologic Height Model
- Extracting elevation data for each monument
- Determining the flood risk level for each monument based on its elevation

## Plotting
The plotting script visualizes the results of the analysis. It does the following:

- Creating an interactive leaflet map to display monuments and their flood risk levels
- Generating summary plots and tables showing the number of at-risk monuments by postal code and flood level
