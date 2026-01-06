## Update Coordinates READ ME 

This notebook provides a reusable function for attaching geographic coordinates (latitude and longitude) to any dataset that contains military base names. It uses the centralized `bases.json` file to look up coordinates and merges them into financial, revenue, or asset datasets.

---

### Purpose

Many of the project’s datasets (financial statements, revenue reports, asset tables) include a `Locations` column but do not contain geographic information.  
This notebook:

- Loads base metadata from `bases.json`
- Matches base names across datasets
- Appends `latitude` and `longitude` columns
- Saves updated datasets for downstream mapping and geospatial visualizations

---

### Core Functionality

The primary function in this notebook is:

```python
add_coordinates(data, bases_json_path, location_column)
