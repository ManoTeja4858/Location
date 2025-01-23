# 🌍 Reverse Geocoding with Python and Geopy

This script performs **reverse geocoding** to extract country, state, and city details from latitude and longitude coordinates in a CSV file. The resulting dataset includes enriched location details for further analysis or reporting.

---

## 📜 Overview

This project uses **Geopy** and **Pandas** to:
1. Read latitude and longitude data from a CSV file.
2. Reverse geocode the coordinates to fetch country, state, and city details.
3. Handle potential issues like invalid coordinates, missing values, and geocoding timeouts.
4. Write the enriched dataset back to a CSV file.

---

## 🚀 How It Works

1. **Input CSV**:  
   The input file (`dateset.csv`) should contain `lat1` and `lon1` columns with latitude and longitude values.

2. **Data Cleaning**:
   - Convert latitude and longitude columns to numeric.
   - Drop rows with missing or invalid coordinates.
   - Ensure coordinates fall within valid geographic ranges:
     - Latitude: `-90` to `90`
     - Longitude: `-180` to `180`

3. **Reverse Geocoding**: 
   - Extract unique latitude and longitude pairs to minimize API calls.  
   - Use the `get_location_details` function to fetch country, state, and city for each unique coordinate.  
   - Implement retry logic with exponential backoff to handle timeouts.

4. **Output CSV**:  
   The enriched dataset (`updated_dataset.csv`) includes three new columns:
   - **Country**: The country name.
   - **State**: The state or region.
   - **City**: The city or locality.

---

## 📂 File Structure

- **Input File**: `dateset.csv`  
  Should include latitude (`lat1`) and longitude (`lon1`) columns.
- **Output File**: `updated_dataset.csv`  
  Includes all original columns plus `Country`, `State`, and `City`.

---

