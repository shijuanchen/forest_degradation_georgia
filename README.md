# Monitoring Temperate Forest Degradation on Google Earth Engine Using Landsat Time Series Analysis

Author: Shijuan Chen     
Date: 08/26/2021

This is a guideline of monitoring forest degradation using the Continuous Change Detection and Classification - Spectral Mixture Analysis (CCDC-SMA) algorithm, visualizing the time series of CCDC-SMA model fits and displaying forest degradation products on Google Earth Engine (GEE), explained in Chen et al., 2021. 

Please click the link below to get access to the GEE repository to run CCDC-SMA:<br /> 
https://code.earthengine.google.com/?accept_repo=users/shijuanchen32/forest_degradation_georgia
(If you are not a GEE user and interested in the apps, please visit: https://shijuanchen32.users.earthengine.app/)

Please cite the code as: [Chen, S., Woodcock, C.E., Bullock, E.L., Arévalo, P., Torchinava, P., Peng, S. and Olofsson, P., 2021. Monitoring temperate forest degradation on Google Earth Engine using Landsat time series analysis. Remote Sensing of Environment, 265, p.112648.](https://www.sciencedirect.com/science/article/pii/S0034425721003680) 

[Click here to get 50-day free access to view and download full-text of the paper without registration](https://authors.elsevier.com/a/1devg7qzStnwW)

The GEE repository includes three parts, apps, codes and utilities. 
1. apps
    - CCDC_SMA_advanced_app: ![Image of CCDC_SMA_advanced_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/CCDC-SMA_advanced_version.png) This app runs the CCDC-SMA model (advanced version). The advanced version uses different indices and thresholds for different types of forests, explained in the paper. To run this app:
      - Enter the GEE asset ids of your study region and forest mask, and specify the value of forest types in the forest mask. Click the "load data" button to add a layer of study region, and "load forest mask" to add a layer of different forest types. 
      - Specify the start and end year of your study period, and the start and end day (in Julian dates) of a year to run analysis. 
      - Check the boxes to export the results as assets in GEE. The default setting would only export the first year of disturbance, since the full segment results will take longer to export.
      - Click "Run CCDC-SMA" to create an export task in the Code Editor Tasks tab. Click the Run button next to the task to start it. 
      - After the task is finished, enter the GEE asset id of the disturbance year and click "view year of change" to display.
   - CCDC_SMA_basic_app: ![CCDC_SMA_basic_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/CCDC-SMA_basic_version.png) This app runs the CCDC-SMA model (basic version). To run the basic version, you only need a forest mask and classification of different forest types is not required. To run this app:
     - Enter the GEE asset ids of your study region and forest mask. Click the "load data" buttons to add the inputs.
     - Specify the timing in the settings.
     - Similar to the advanced version, run CCDC-SMA, export and view the results. 
   - Display_products_app: ![Display_products_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/display_products.png) This app displays the products of forest degradation, deforestation and land cover. 
     - Click the "Display" buttons to display each product. For annual product, select a year to display.
   - Time_series_plotter: ![Time_series_plotter](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/display_ts_CCDC_SMA.png)
   ![Time_series_plotter](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/display_ts_CCDC_SMA_an.png) This app shows the Landsat time series and CCDC-SMA model fits. To run the app:
     - Specify the start and end date in YYYY-MM-DD format, and the start and end day of a year in the analysis.
     - Select an index to display. NDFI and the fraction of endmembers will be used to run the CCDC-SMA model, but only the time series of the selected index will show up in the time series plot. 
     - Click a point on the map to display the time series and model fits. 
     - Click a point on the time series to add the natural-looking Landsat image of this point.
     - You can also explore the pre-loaded four examples of forest degradation. In the search box, enter the id of examples (id ranges from 1 to 4). Click the red point on the map to display the time series of the examples.  
     - Use "Reset" button to reset the map panel.
2. codes
   - CCDC_SMA_advanced: This script allows users to run CCDC-SMA (advanced) directly without using the apps. The algorithm is the same with the one used in the apps.
   - CCDC_SMA_basic: This script allows users to run CCDC-SMA (basic) directly without using the apps. The algorithm is the same with the one used in the apps.
3. utilities
   - ut_CCDC_SMA: functions to retrieve CCDC-SMA coefficients. 
   - ut_plotter_search: functions used in the time series plotter
   - ut_workflow: functions used to run the CCDC-SMA and classify segments.







