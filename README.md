# README - Optimizing eVTOL Time Scheduling through Origin-Destination and Temporal Data Analysis

## Overview
This repository contains the code and datasets used for the study on optimizing the scheduling and station placement of electric vertical take-off and landing (eVTOL) vehicles. The research focuses on integrating urban mobility data to determine optimal eVTOL routes and schedules in São Paulo and New York City.

## Repository Structure
- `NY/` - Contains the NY analysis and its data.
- `São Paulo/` - Contains the São Paulo analysis and its data.
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
### Step 1: Filter Origin-Destination Pairs and execute K Means for clustering
Filters Uber and Taxi data to extract OD pairs with distances exceeding 30 km and 
it uses K-Means clustering to group OD points and assigns the closest heliport as a station.

```
 "City"/1_Part_notebook_stations_zone_elbow.ipynb
```

### Step 2: Determine Peak Usage Times
Utilizes Google API to identify peak travel times for OD pairs.
```
 "City"/2_Part_notebook_stations_schedule.ipynb
```

### Step 3: Generate Final Schedule
Cleans data and exports final station locations and schedules in `.csv` format.
```
"City"/3_Part_notebook_stations_schedule.ipynb
```

## Output Files
- `outout.csv` - Lists of the schedules for all the stations.

## Usage Notes
- The repository allows for customization, such as modifying clustering parameters and integrating additional datasets.
- The Google API key must be added in `2_Part_notebook_stations_schedule.ipynb` to enable real-time data retrieval.

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

