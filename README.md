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

Add dependencies to `requirements.txt` as needed. It initially contains no packages.

## Organization

- Store raw and processed datasets in `data`.
- Add Python scripts and Jupyter notebooks to `code`.
- Save generated reports and visualizations to `reports`.
