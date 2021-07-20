# Monitoring Temperate Forest Degradation on Google Earth Engine Using Landsat Time Series Analysis

(Improvements to be made. Expected to be ready by August 15th, 2021.)

Author: Shijuan Chen     
Date: 07/20/2021

Please click the link below to get access to the GEE repository named 'users/shijuanchen32/forest_degradation_georgia':
https://code.earthengine.google.com/?accept_repo=users/shijuanchen32/forest_degradation_georgia

Please cite the code as: Chen, S., Woodcock, CE., Bullock E., Arevalo, P., Torchinava, P., Peng, S. and Olofsson P. (2021). Monitoring Temperate Forest Degradation on Google Earth Engine Using Landsat Time Series Analysis. Remote Sensing of Environment. (In Minor Revision)

The respository includes three parts, apps, codes and utilities. 
1. apps
   - CCDC_SMA_advanced_app: The app runs the CCDC-SMA model (advanced version). The advanced version uses different indices and thresholds for different types of forests, explained in the paper. To run this app:
      - Enter the GEE asset ids of your study region and forest mask, and specify the value of forest types in the forest mask. Click the "load data" button to add a layer of study region, and "load forest mask" to add a layer of different forest types. 
      - Specify the start and end year of your study period, and the start and end day (in Julian dates) of a year to run analysis. 
      - Check the boxes to export the results as assets in GEE. The default only export the first year of disturbance, since the full segment results will take longer to export.
      - Click "Run CCDC-SMA" to create an export task in the Code Editor Tasks tab. Click the Run button next to the task to start it. 
      - After the task is finished, enter the GEE asset id of the disturbance year and click "view year of change" to display.
   - CCDC_SMA_basic_app: The app runs the CCDC-SMA model (basic version). To run the basic version, you only need a forest mask and classification of different forest types is not required. To run this app:
     - Enter the GEE asset ids of your study region and forest mask. Click the "load data" buttons to add the inputs.
     - Specify the timing in the settings.
     - Similar to the advanced version, run CCDC-SMA, export and view the results. 
   - Display_products_app: The app displays the products of forest degradation, deforestation and land cover. 
     - Click the "Display" buttons to display each product. For annual product, select a year to display.
   - Time_series_plotter:
2. codes
   - CCDC_SMA_advanced
   - CCDC_SMA_basic 
3. utilities
   - ut_CCDC_SMA: functions to retrive CCDC-SMA coefficients. 
   - ut_plotter_search: functions used in the time series plotter
   - ut_workflow: functions functions used to run the CCDC-SMA and classify segments.







