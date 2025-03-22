# shallowML_regression
Assessing different models and approaches for predicting SST

These notebooks will take you through the various (non exhaustive) options available for predicting Sea Surface Temperature (SST) using co-variables including Sea Surface Height (SSH), Salinity (SSS), Currents (Vu and Vu), and Ocean Mixed Layer Thickness (MLD). We will also begin to integrate 'time' into our training to assess if this helps the model learn, as well as categorical variables 'season' and ENSO state 'MEI'.

From the Copernicus Marine Service (CMEMS), training datasets for these notebooks were taken from the freely available Level-4 Global Ocean Physics Reanalysis Product (ID: GLOBAL_MULTIYEAR_PHY_001_030; daily). Testing data was sourced from the freely available Level-4 Global Ocean Physics Analysis and Forecast Product (ID: GLOBAL_ANALYSISFORECAST_PHY_001_024; daily). In my examples, I used timeseries data of the listed co-variables taken from the Gulf Stream at POINT (-80.00 30.00).

The categorical ENSO data -- Multivariate ENSO Index Version 2 (MEI.v2)-- were provided at  no cost by NOAA:
https://psl.noaa.gov/enso/mei/

