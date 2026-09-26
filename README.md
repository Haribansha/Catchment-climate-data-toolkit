# Catchment Climate Data Toolkit

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](COLAB_LINK_AFTER_YOU_UPLOAD)

A reproducible Google Colab workflow for delineating an upstream catchment from a U.S. outlet coordinate, mapping the upstream stream network, and extracting catchment-area-weighted daily PRISM precipitation and temperature.

## What it does

1. Accepts outlet latitude/longitude and a date range.
2. Hydrolocates the outlet to the USGS NHDPlus network using NLDI.
3. Delineates the upstream basin and retrieves upstream tributary flowlines.
4. Creates an interactive Folium map.
5. Downloads daily 4-km PRISM grids for precipitation, minimum temperature, and maximum temperature.
6. Calculates catchment-area-weighted daily meteorology.
7. Exports catchment, streams, outlet, interactive map, and a clean CSV.

## Example

Default example outlet:

- Latitude: `40.605278`
- Longitude: `-88.898889`

Change the values in the **USER SETTINGS** cell to analyze another CONUS outlet.

## Outputs

- `catchment.geojson`
- `upstream_streams.geojson`
- `outlet.geojson`
- `catchment_map.html`
- `PRISM_Catchment_Average_YYYY-MM-DD_to_YYYY-MM-DD.csv`

## Data sources

### USGS NLDI / NHDPlusV2
USGS Network Linked Data Index (NLDI) is used for hydrolocation, upstream basin retrieval, and network navigation.

Documentation: https://api.water.usgs.gov/docs/nldi/

### PRISM Climate Data
Daily 4-km PRISM grids are used for precipitation and temperature. PRISM daily grids are served one date/variable per request, so long date ranges can take time. The notebook caches downloaded ZIP files so reruns do not download the same grids again.

PRISM: https://prism.oregonstate.edu/

## Method

For a meteorological variable X, the catchment value is computed as an area-weighted mean:

    X_bar = sum(X_i * A_i) / sum(A_i)

where `X_i` is the PRISM value of grid cell `i` and `A_i` is the area of that grid cell intersecting the catchment.

The workflow uses a projected equal-area CRS when calculating intersection areas.

## Important limitations

- NLDI basin boundaries are based on NHDPlusV2 and are not a substitute for project-specific high-resolution DEM delineation.
- Always visually verify that the outlet snapped to the intended stream.
- PRISM is gridded climate data; the output is not an observed weather-station record.
- Very long daily PRISM periods involve thousands of official grid requests. Start with a short test period before requesting decades.
- Data availability and service behavior can change; consult the official USGS and PRISM documentation.

## Run in Google Colab

After uploading this repository to GitHub, replace `YOUR_USERNAME` below:

    https://colab.research.google.com/github/YOUR_USERNAME/catchment-climate-data-toolkit/blob/main/Catchment_PRISM_Extractor.ipynb

Then replace `COLAB_LINK_AFTER_YOU_UPLOAD` at the top of this README with that URL.

## Local installation

    pip install -r requirements.txt

## Repository structure

    catchment-climate-data-toolkit/
    ├── Catchment_PRISM_Extractor.ipynb
    ├── README.md
    ├── requirements.txt
    ├── LICENSE
    ├── CITATION.cff
    ├── .gitignore
    ├── examples/
    │   └── README.md
    ├── images/
    │   └── README.md
    └── website/
        └── project-card.html

## Suggested citation

If you use this workflow in research, please cite this repository and the underlying USGS NLDI/NHDPlus and PRISM datasets/services as appropriate.

## Author

Haribansha Timalsina, EIT  
Ph.D. Candidate, Agricultural & Biological Engineering  
University of Illinois Urbana-Champaign

## License

MIT License. See `LICENSE`.
