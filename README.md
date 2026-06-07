# Los Angeles Crime Data Analysis
## Project Objectives and Key Findings

* **Peak Temporal Distribution:** Calculated the hourly frequency of reported incidents across the municipality to determine the exact hour experiencing the highest volume of criminal activity (stored as `peak_crime_hour`).
* **Spatial Analysis of Night Crimes:** Filtered and aggregated incident records occurring between 22:00 and 03:59 to identify the specific geographic LAPD patrol division reporting the highest density of nighttime offenses (stored as `peak_night_crime_location`).
* **Demographic Stratification:** Segmented and binned victim age distributions into seven specific cohorts ("0-17", "18-25", "26-34", "35-44", "45-54", "55-64", and "65+") to generate a frequency distribution mapping vulnerability metrics across age intervals (stored as `victim_ages`).

## Environment and Dependencies

* **Language:** Python 3.x
* **Core Libraries:** Pandas, NumPy, Matplotlib, Seaborn
* **Execution Environment:** Jupyter Notebook / DataCamp Workspace

## Data Pipeline and Source Note

The primary dataset (`crimes.csv`) possesses a footprint of approximately 27MB, exceeding standard web-interface serialization thresholds. To optimize repository storage and accessibility, the file has been compressed into a standard ZIP archive (`workspace.zip`). 

The analytical environment utilizes a vectorized execution block allowing Pandas to parse and decompress the source format directly in memory during runtime:

```python
import pandas as pd
crimes = pd.read_csv('workspace.zip')
