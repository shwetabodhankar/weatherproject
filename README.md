# Weather

We will use the data science methodology to investigate whether it rains more in Seattle, WA than in St. Louis, MO. The problem is simple; my parents think that it rains too much in Seattle. I want to use data to determine whether it rains more in Seattle, WA than in St. Louis, MO.

## Project structure

```text
weather/
|-- data/              # Raw and processed data
|-- code/              # Jupyter notebooks and Python scripts
|-- reports/           # Generated reports and visualizations
|-- requirements.txt   # Python dependencies
`-- README.md          # Project documentation
```

## Getting started

From the `weather` directory, create a virtual environment and install dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Open [Weather_Data.ipynb](code/Weather_Data.ipynb) in VS Code or Jupyter, select
the `.venv` Python kernel, and run all cells from top to bottom. The notebook
supports running from either the project root or the `code` directory.

## Data analysis

[Weather_Data.ipynb](code/Weather_Data.ipynb) performs the analysis:

1. Inspects the raw files, column types, stations, date ranges, duplicates, and missing values.
2. Converts dates and precipitation to appropriate types and restricts observations to 2018–2022.
3. Compares Seattle station `US1WAKG0225` with St. Louis Lambert airport
   station `USW00013994`, rather than combining many St. Louis stations.
4. Audits missing calendar dates and missing precipitation, without imputing unknown rainfall as zero.
5. Joins the cities on shared dates with valid precipitation, reshapes to tidy
   long format, and derives year, month, and a measurable-precipitation indicator.
6. Compares precipitation amount and rainy-day frequency using summary tables
   and graphs, and discusses coverage and station-selection limitations.

The clean data file is [weather_clean.csv](data/weather_clean.csv), with one row
per city per matched date. Precipitation is in inches, as confirmed by the project
owner. The notebook writes summary tables and two figures to [reports](reports/).
All results describe the matched observations, not complete annual rainfall totals.
The optional hypothesis tests are not included; the analysis uses descriptive
statistics and graphs.

### Findings

Across 1,636 shared valid dates in 2018–2022, Seattle had measurable precipitation
on 51.4% of days versus 32.6% in St. Louis. St. Louis had the higher mean daily
precipitation: 0.134 inches versus 0.112 inches in Seattle. In this sample, Seattle
was wetter by frequency, but St. Louis was wetter by amount. Missing dates, station
differences, and the short study period limit broader conclusions.

The raw inputs are [seattle_rain.csv](data/seattle_rain.csv) and
[stl_rain.csv](data/stl_rain.csv). Their station identifiers and column names match
NOAA GHCN-Daily / Climate Data Online conventions, but the original download links
and export settings were not supplied. Relevant references are
[NOAA Climate Data Online](https://www.ncei.noaa.gov/cdo-web/) and the
[GHCN-Daily documentation](https://www.ncei.noaa.gov/pub/data/ghcn/daily/readme.txt).
See the notebook for the full provenance caveat and cleaning decisions.

## Organization

- Store raw and processed datasets in `data`.
- Add Python scripts and Jupyter notebooks to `code`.
- Save generated reports and visualizations to `reports`.
