# Christchurch-housing-suitability-analysis
GIS and Python project evaluating residential suitability for international student families in Christchurch through network accessibility analysis and multi-criteria spatial modelling.

<img width="865" height="963" alt="image" src="https://github.com/user-attachments/assets/1ad7f0bd-99c1-478e-936e-8ab573bdc057" />

## Project Overview
This project develops a GIS-based housing suitability model for international student families studying at the University of Canterbury.

Unlike conventional housing analyses that focus solely on commuting, this project incorporates the daily travel needs of families with school-aged children by evaluating accessibility to the university, primary schools, and public transport.

The workflow integrates open geospatial data, pedestrian network analysis, and weighted spatial modelling to identify suitable residential areas across Christchurch.

## Objectives
The project identifies residential locations that simultaneously satisfy three walking accessibility criteria:

| Destination              | Walking Threshold |
| ------------------------ | ----------------: |
| University of Canterbury |      ≤ 40 minutes |
| Primary School           |      ≤ 15 minutes |
| Bus Stop                 |      ≤ 15 minutes |

Accessibility layers are combined through weighted overlay analysis to produce a five-level housing suitability map.

## Study Area
Christchurch, New Zealand

## Technologies

| Category         | Tools                     |
| ---------------- | ------------------------- |
| Programming      | Python                    |
| GIS Libraries    | GeoPandas, Shapely        |
| Network Analysis | OSMnx, NetworkX           |
| Data Processing  | Pandas, NumPy             |
| Mapping          | Matplotlib                |
| Development      | Jupyter Notebook, VS Code |

## Data Sources
1) Stats NZ – SA2 and Meshblock boundaries
2) OpenStreetMap – pedestrian road network, university campus and bus stops
3) Wikipedia + OpenStreetMap – primary school locations

#### Coordinate Reference System:
NZTM2000 (EPSG:2193)

## Workflow
<img width="2000" height="2828" alt="image" src="https://github.com/user-attachments/assets/6fd96d2f-93b4-45e4-87f4-3a144e05366f" />

## Methodology
#### 1. Data preprocessing
1) Standardised all datasets into NZTM2000 (EPSG:2193)
2) Clipped layers to the study area
3) Built a pedestrian road network
#### 2. Network accessibility modelling
Walking isochrones were generated using shortest-path analysis:
1) University (40 minutes)
2) Primary schools (15 minutes)
3) Bus stops (15 minutes)
#### 3. Multi-criteria evaluation
Accessibility layers were normalised (0–1) and combined using weighted overlay.

| Criterion      | Weight |
| -------------- | -----: |
| Primary School |   0.50 |
| University     |   0.35 |
| Bus Stop       |   0.15 |

## Results

#### 1. University Accessibility

<img width="865" height="941" alt="image" src="https://github.com/user-attachments/assets/03509af6-8589-4f92-8b20-545cb9975ee0" />

#### 2. Primary School Accessibility

<img width="865" height="941" alt="image" src="https://github.com/user-attachments/assets/5367ac9c-ccc7-4694-bbb0-8a92a3cb6d57" />

#### 3. Bus Stop Accessibility

<img width="865" height="941" alt="image" src="https://github.com/user-attachments/assets/6b25fa6a-4213-4248-9a1d-a69cc434f4c2" />

#### 4. Final Housing Suitability

<img width="865" height="963" alt="image" src="https://github.com/user-attachments/assets/99799cf9-116e-4a37-b5f3-63b1fa62f98b" />

## Key Findings

1) High suitability areas are concentrated in Ilam North, Fendalton, and Jellie Park.
2) Public transport accessibility is generally high across Christchurch.
3) Primary school accessibility is the dominant factor influencing residential suitability.
4) The identified high-suitability areas closely align with existing international student residential patterns.

## Limitations
1) OpenStreetMap data may contain incomplete or outdated information.
2) A constant walking speed was assumed for all users.
3) Housing prices, neighbourhood safety, and green space were not included in the suitability model.

## Future Improvements
1) Incorporating rental prices and housing availability
2) Including neighbourhood safety and green space indicators
3) Applying the workflow to other cities
4) Developing an interactive WebGIS application

## Skills Demonstrated
1) GIS Spatial Analysis
2) Python Geospatial Programming
3) Network Accessibility Analysis
4) Multi-Criteria Decision Analysis (MCDA)
5) GeoPandas
6) OSMnx
7) NetworkX
8) Spatial Data Processing
9) Cartographic Visualisation
10) Reproducible GIS Workflow
