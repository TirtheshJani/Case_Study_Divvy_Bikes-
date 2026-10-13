# Divvy Bikes Case Study: 2023 Year in Review

A one-page Tableau dashboard of 4,331,707 Divvy bike-share trips taken in Chicago in 2023, built to compare how annual members and casual riders use the system.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

The case study starts from one question: "How does a bike-share navigate speedy success?" I checked a year of Divvy trip records with Python and pandas in Jupyter Notebook, then built a Tableau dashboard that breaks 2023 ridership down by month, weekday, hour, trip length, and destination station.

The finished dashboard is in this repo as [`Divvy a Year in Review 2023.pdf`](Divvy%20a%20Year%20in%20Review%202023.pdf), and the interactive version is on [Tableau Public](https://public.tableau.com/views/DivvyBikes_17079314381930/DivvyaYearinReview2023). Only the exported dashboard is committed. The data-prep notebooks and the Tableau workbook are not.

## Dashboard design

- Seven panels on one letter-size page (11 x 8.5 in): Rides by Month, Average Ridership by day, Rides by Hour, Supply and Demand (printed as "Suppy and Demand"; it plots net demand), Rides with Trip Times, Rides by Day, and a Hot destinations station map.
- Most panels split rides into two series, drawn in red and black. Three controls at the top (Top Stations, set to 50; Day and User Type, both set to All) decide what is shown.
- Rides by Hour and Supply and Demand are faceted by day of week, with one panel per day from Sunday to Saturday.
- Trip length is a packed bubble chart of duration buckets. The station map sits on a Mapbox / OpenStreetMap basemap.
- Exported from Tableau 2024.1. The PDF metadata records the creator as `Tableau 20241.24.130.2035` and the creation date as 2024-02-20 (UTC).

## What the dashboard shows

These figures are taken directly from the dashboard.

| Measure | Value | Where it appears in the PDF |
|---|---|---|
| Trips in 2023 | 4,331,707 | Summary text, top left |
| Share of trips made by annual members | 60% | Summary text, top left |
| Largest trip-length bucket | 0:15 minutes, labeled 48.97% (red bubble) and 20.23% (black bubble) | Rides with Trip Times |
| Next labeled bucket | 0:30 minutes, 11.91% (red bubble) | Rides with Trip Times |

Two more patterns can be read from bar and area heights, although the PDF prints no values for them. In Average Ridership by day, the red bars are tallest Tuesday to Thursday, while the black segment and the stacked total are largest on Saturday. In Rides by Month, the highest point of the chart and the top of the red area both fall in August.

The static export does not include a color legend.

## Recommendations from the original write-up

The original README (commit `85cf0b8`, February 2024) made three recommendations: membership campaigns aimed at casual riders, weekend promotions such as guided tour routes, and matching bike and dock supply to peak usage times. The analysis behind them is not committed, so treat them as the author's conclusions rather than results you can check here.

## How it was built

The same write-up describes the workflow. The source was Divvy's trip data in CSV form, one row per trip, including these columns:

- ride ID and rideable type
- start and end times
- start and end station names and IDs
- station latitude and longitude
- rider type (member or casual)

The trips were checked in Python with pandas, in Jupyter Notebook, for completeness, accuracy, consistency, and correct column data types. The checked data then went into Tableau for the dashboard.

## Viewing the dashboard

Nothing needs to be installed or run. The [Tableau Public](https://public.tableau.com/views/DivvyBikes_17079314381930/DivvyaYearinReview2023) version lets you try the filters in a browser. To read the static export, clone the repo and open `Divvy a Year in Review 2023.pdf` in any PDF viewer.

```bash
git clone https://github.com/TirtheshJani/Case_Study_Divvy_Bikes-.git
cd Case_Study_Divvy_Bikes-
```

## Repository layout

```text
Case_Study_Divvy_Bikes-/
├── Divvy a Year in Review 2023.pdf   # one-page Tableau dashboard export (Feb 2024)
├── README.md
└── LICENSE                           # MIT
```

## Status

The PDF was exported in February 2024 and has not been updated in this repo since. Three things are not in the repo: the raw trip CSVs, the data-check notebooks, and the Tableau workbook (`.twb` or `.twbx`). You can read the figures above from the PDF, but you cannot regenerate them from this repository.

## Data and acknowledgements

The trip data comes from Divvy, Chicago's bike-share system, which the original write-up describes as operated by Lyft in partnership with the City of Chicago. Map tiles in the Hot destinations panel are © 2024 Mapbox © OpenStreetMap, as credited on the dashboard.

## Author and license

Tirthesh Jani ([GitHub](https://github.com/TirtheshJani), [LinkedIn](https://www.linkedin.com/in/tirthesh-jani)).

Released under the MIT License. See [LICENSE](LICENSE).
