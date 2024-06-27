# Analysis of Air Quality Index in Mexico City Metropolitan Area (CDMX) from 2019 to 2023

---

## Overview

This project analyzes the Air Quality Index (AQI) data for the Mexico City Metropolitan Area (CDMX) from 2019 to 2023. The data, provided by the Secretaría del Medio Ambiente (SEDEMA), includes hourly AQI readings by zone and atmospheric pollutant according to the environmental standard NADF-009-AIRE-2017. The analysis involves data preprocessing, visualization, and statistical techniques to assess the air quality over the specified period.

---

## Dataset Overview and Dimensions of Variability

### Primary Variable
The primary variable in this dataset is the Air Quality Index (AQI) for different pollutants, which includes hourly measurements of AQI values for various atmospheric contaminants.

### Dimensions of Variability
1. **Contaminants**: The dataset includes AQI measurements for six different pollutants:
   - Ozone (O3)
   - Sulfur Dioxide (SO2)
   - Nitrogen Dioxide (NO2)
   - Carbon Monoxide (CO)
   - PM10 (particulate matter with a diameter of 10 micrometers or less)
   - PM2.5 (particulate matter with a diameter of 2.5 micrometers or less)

2. **Locations**: Measurements are taken across five regions:
   - Noroeste (Northwest)
   - Noreste (Northeast)
   - Centro (Center)
   - Suroeste (Southwest)
   - Sureste (Southeast)

3. **Time**: The dataset spans from 2019 to 2023, with hourly AQI readings corresponding to specific dates and hours.

---

## Overview of the Project

### Data Loading and Preparation
1. **Loading Data**: CSV files from 2019 to 2022 are loaded into Pandas DataFrames, skipping the first eight rows to bypass metadata.
2. **Data Concatenation**: The data from all four years is concatenated into a single DataFrame.
3. **Datetime Column Creation**: A new datetime column is created by combining the 'Fecha' and 'Hora' columns.

### Data Analysis
1. **Ozono Centro Region Time Series**: A line graph is generated for the 'Ozono Centro' variable, visualizing the time series of ozone levels in the Centro region.

2. **Ozone Index Across Different Regions**: A single graph is created to plot the ozone index for different locations, with different colors representing different regions.

3. **AQI for Various Contaminants and Regions**: A multi-panel graph is generated, where each panel displays a different pollutant and the lines represent different regions.

### Data Imputation and Moving Averages
1. **Data Imputation**: Missing data for O3 in the southeast region is filled using linear interpolation.
2. **Moving Averages**: A 7-day moving average is applied to the time series using both uniform and triangular kernels, and the results are plotted.

### Moving Averages for Different Periods
1. **Rectangular Kernel Convolution**: Moving averages for 15 days, 1 month, and 3 months are computed using rectangular kernels and the `np.convolve` function.
2. **Plotting Convolutions**: The results of the convolutions for different pollutants and regions are visualized in multi-panel graphs.

### Generation of 4D Array for Moving Averages
1. **4D Array Creation**: A 4-dimensional array is generated to store moving averages for different periods. The dimensions represent time, pollutant, zone, and moving average length.
2. **Applying Convolutions**: Convolutions are applied to the dataset, and results are stored in the 4D array.
3. **Visualizing Results**: The results are visualized in figures showing the moving averages for different periods.

---

## Possible Applications
- **Environmental Monitoring**: Understanding the temporal and spatial variability of air quality can help in monitoring pollution levels and identifying trends.
- **Public Health**: Analyzing AQI data can provide insights into potential health risks associated with air pollution.
- **Policy Making**: The analysis can aid policymakers in formulating strategies to mitigate air pollution and protect public health.
- **Research**: The dataset and analysis can serve as a basis for further research in environmental science and public health.

---

## Dependencies and Resources

### Libraries
- **NumPy**: For numerical operations and array manipulations.
- **Pandas**: For data loading, cleaning, and manipulation.
- **Matplotlib**: For data visualization and plotting.
- **Warnings**: To manage and filter warning messages.

### Data Source
- The data is sourced from SEDEMA and is provided in CSV files named `indice_20XX.csv` for each year.

---

## Conclusion
This project provides a comprehensive analysis of the air quality in CDMX from 2019 to 2023, utilizing advanced data manipulation and visualization techniques. By exploring the variability in AQI across different pollutants, regions, and time periods, it offers valuable insights for environmental monitoring, public health, and policy-making.