# Melbourne Tourist Explorer

## Overview
**Melbourne Tourist Explorer** is an interactive Shiny web application that helps users explore Melbourne’s landmarks, restaurants, public transport, and real-time weather.  
It integrates open datasets from [VIC.GOV.AU](https://discover.data.vic.gov.au/) and [City of Melbourne Open Data](https://data.melbourne.vic.gov.au/), combined with live weather data from the [OpenWeather API](https://openweathermap.org/api).

This project was developed for **SCIE90017 – Information Visualisation (The University of Melbourne)**, aiming to make city data more intuitive and engaging for non-technical users.

---

## Requirements

### R Version
- R ≥ 4.2  
- RStudio recommended

### Required Packages
Install these packages before running:
```r
install.packages(c(
  "shiny", "leaflet", "leaflet.extras", "dplyr",
  "readr", "sf", "plotly", "ggplot2", "jsonlite",
  "lubridate", "DT", "shinyjs", "memoise", "rlang", "RColorBrewer"
))```

## API Setup

The app uses the **OpenWeather API** to display real-time and forecast weather.  
Before running the app, you must export the API key to your environment.

### macOS / Linux
Open **Terminal** and run:
```bash
export OPENWEATHER_KEY="d1eda37b18dcabae86e4c4be437d17e3"
open -a RStudio

