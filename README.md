🌏 Melbourne Tourist Explorer
🏙️ Overview

Melbourne Tourist Explorer is an interactive Shiny web application that helps users explore Melbourne’s key landmarks, restaurants, transport accessibility, and real-time weather.
It combines open datasets from VIC.GOV.AU and City of Melbourne Open Data, with live weather data from OpenWeather API.

This project was developed for SCIE90017 Information Visualisation (The University of Melbourne), aiming to make city data more engaging and accessible.

📂 Project Structure
app_final/
├── app.R                   # Main Shiny application
├── data_preprocess.R        # Offline preprocessing script
├── data/
│   ├── landmarks_clean.geojson
│   ├── cafes_restaurants_2022_2023.csv
│   ├── bus_stops.geojson
│   ├── municipal-boundary.geojson
│   └── daily_totals.csv
├── www/
│   ├── style.css
│   └── (icons / images)
└── README.md

⚙️ Requirements
🧩 R Version

R ≥ 4.2

RStudio recommended

📦 Required R Packages

Install the following packages before running:

install.packages(c(
  "shiny", "leaflet", "leaflet.extras", "dplyr",
  "readr", "sf", "plotly", "ggplot2", "jsonlite",
  "lubridate", "DT", "shinyjs", "memoise", "rlang", "RColorBrewer"
))

🔑 API Setup (Important)

The app uses the OpenWeather API for live and forecast weather data.
Before running the app, you need to export the API key.

macOS / Linux

Open Terminal and run:

export OPENWEATHER_KEY="d1eda37b18dcabae86e4c4be437d17e3"
open -a RStudio

Windows (PowerShell)
setx OPENWEATHER_KEY "d1eda37b18dcabae86e4c4be437d17e3"


Then reopen RStudio to make sure the key is loaded.

▶️ Run the App

Unzip the folder app_final.zip

Open RStudio

Set the working directory, for example:

setwd("~/Desktop/app_final")


(Optional) Run preprocessing script to regenerate cleaned data:

source("data_preprocess.R")


Run the main app:

shiny::runApp("app.R")


The app will automatically open in your browser (e.g. http://127.0.0.1:xxxx
)

🗺️ Data Sources
Dataset	Source	Description
Landmarks	City of Melbourne Open Data
	Landmarks and points of interest
Cafes & Restaurants	VIC.GOV.AU Data Directory
	Business listings for 2022–2023
Bus Stops & Tram Tracks	VIC.GOV.AU Transport Data
	Public transport information
City Boundary	City of Melbourne GIS
	Municipal boundary of Melbourne
Pedestrian Counts	City of Melbourne Sensors API
	Used for crowd and trend analysis
Weather Data	OpenWeather API
	Real-time and forecast weather
🧠 System Architecture

Our system follows a four-layer structure:

Data Input Layer – Automatically loads and caches datasets from open APIs

Processing Layer – Cleans, filters, and standardises all data via data_preprocess.R

Storage Layer – Uses lightweight CSV and GeoJSON files for fast local access

Visualisation Layer – Built with:

Shiny (interface and logic)

Leaflet / Plotly (interactive maps and charts)

Tableau Dashboard (embedded for trend analytics)

🌦️ Notes

If OpenWeather API fails, the app automatically switches to MET Norway.

All datasets are public and contain no personal information.

Tested on macOS Sonoma and Windows 11.

👥 Authors

Team: Melbourne Tourist Explorer

[Your Name]

[Teammate 1]

[Teammate 2]

[Teammate 3]

The University of Melbourne – SCIE90017 Information Visualisation (2025)
