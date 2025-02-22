# README - Optimizing eVTOL Time Scheduling through Origin-Destination and Temporal Data Analysis

## Overview
This repository contains the code and datasets used for the study on optimizing the scheduling and station placement of electric vertical take-off and landing (eVTOL) vehicles. The research focuses on integrating urban mobility data to determine optimal eVTOL routes and schedules in São Paulo and New York City.

## Repository Structure
- `data/` - Contains the raw datasets used for analysis.
- `scripts/` - Python scripts used for data processing and analysis.
- `results/` - Output datasets including eVTOL schedules and station locations.
- `README.md` - This file, providing details on how to use the code.

## Data Sources
- **Uber Movement Data**: Extracted for São Paulo.
- **NYC Taxi Data**: Obtained from the NYC Open Data portal.
- **Helicopter Path Data**: São Paulo’s helicopter corridors from the Brazilian government.
- **Heliport Data**: FAA data for New York City heliports.
- **Google API**: Used to gather real-time traffic data for station scheduling.

## Requirements
The project uses Python and requires the following libraries:
```bash
pip install pandas numpy scikit-learn requests folium
```
Additionally, a Google API key is needed to access traffic data.

## Code Execution
### Step 1: Filter Origin-Destination Pairs
Filters Uber and Taxi data to extract OD pairs with distances exceeding 30 km.
```bash
python scripts/filter_od_pairs.py
```

### Step 2: Cluster Data & Identify Stations
Uses K-Means clustering to group OD points and assigns the closest heliport as a station.
```bash
python scripts/cluster_od_pairs.py
```

### Step 3: Determine Peak Usage Times
Utilizes Google API to identify peak travel times for OD pairs.
```bash
python scripts/get_peak_times.py
```

### Step 4: Generate Final Schedule
Cleans data and exports final station locations and schedules in `.csv` format.
```bash
python scripts/generate_schedule.py
```

## Output Files
- `eVTOL_routes.csv` - Contains the final optimized flight routes.
- `eVTOL_schedules.csv` - Provides scheduled take-off times for each route.
- `eVTOL_stations.csv` - Lists heliport locations designated as eVTOL stations.

## Usage Notes
- The repository allows for customization, such as modifying clustering parameters and integrating additional datasets.
- The Google API key must be added in `get_peak_times.py` to enable real-time data retrieval.

## Contributors
- **Carolina Rutili Lima** - Data analysis & manuscript preparation.
- **Fernando J. O. Moreira** - Review & validation.
- **Marcos Maximo** - Technical supervision.

## Citation
If using this code or dataset in your research, please cite:
```
@article{evtol2024,
  author = {Lima, C. R. and Moreira, F. J. O. and Maximo, M. R. O. A.},
  title = {Optimizing eVTOL Time Scheduling through Origin-Destination and Temporal Data Analysis},
  journal = {Data Science and Management},
  year = {2024}
}
```

## License
This project is licensed under the MIT License - see the LICENSE file for details.

For further inquiries, contact: [GitHub Repository](https://github.com/FLYMOV-ERC/Data_evtols/)

