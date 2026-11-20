# Sri Lanka Geo Service

This project is based on [Open Geo Service](https://open-geo-service.dhis2.org/) and provides climate data for Sri Lanka, including ERA5-Land reanalysis, CHIRPS3 precipitation, PM2.5 air quality, and WorldPop population data.

## Installation

1. **Clone the repository:**
   ```sh
   git clone https://github.com/MasterMaps/sri-lanka-geo-service.git
   cd sri-lanka-geo-service
   ```

2. **Install dependencies:**
   ```sh
   make install
   ```

3. **Configure environment:**
   ```sh
   cp .env.example .env
   # Edit .env and set GEOSERVICE_CONFIG to the absolute path of geoservice.yaml
   # Set PROJ_DATA to the rasterio proj_data path in your venv
   ```

## Usage

```sh
make run
```

The API starts at http://localhost:8002. Visit `/manage` to ingest datasets.

## Available Datasets

| Dataset | Period | Source |
|---|---|---|
| 2m temperature (ERA5-Land) | Hourly | DestinE Earth Data Hub |
| Total precipitation (ERA5-Land) | Hourly | DestinE Earth Data Hub |
| Total precipitation (CHIRPS3) | Daily | CHC UCSB |
| Total population (WorldPop) | Yearly | WorldPop |
| Total population 1 km (WorldPop Global2) | Yearly | WorldPop |
| Elevation (Copernicus DEM GLO-30) | Static | AWS Open Data |
| Land Cover (ESA CCI) | Yearly | Copernicus CDS |
| Land Cover (MODIS MCD12Q1) | Yearly | NASA MODIS |
| Gross Primary Production (CLMS) | Dekadal | Copernicus CLMS |
| Vegetation Index NDVI (CLMS) | Dekadal | Copernicus CLMS |
| PM2.5 Surface Concentration (CAMS EAC4) | 3-hourly | Copernicus ADS |
| PM2.5 Surface Concentration (CICERO) | Daily, 2020-03 to 2023-12 | CICERO, a local file |
| PM2.5 population exposure (CICERO x WorldPop 1 km) | Daily | Derived with the `population_exposure` workflow |
