# Monitoring Temperate Forest Degradation on Google Earth Engine Using Landsat Time Series Analysis
(Improvements to be made. Expected to be ready by August 15th, 2021.)
Author: Shijuuan Chen     Date: 07/20/2021
Please click the link below to get access to the GEE repository named 'users/shijuanchen32/forest_degradation_georgia':
https://code.earthengine.google.com/?accept_repo=users/shijuanchen32/forest_degradation_georgia

Please cite the code as: Chen, S., Woodcock, CE., Bullock E., Arevalo, P., Torchinava, P., Peng, S. and Olofsson P. (2021). Monitoring Temperate Forest Degradation on Google Earth Engine Using Landsat Time Series Analysis. Remote Sensing of Environment. (In Minor Revision)

The respository includes three parts, apps, codes and utilities. 
1. apps
   - CCDC_SMA_advanced_app: The app to run the CCDC-SMA model (advanced version). The advanced version uses different indices and thresholds for different types of forests, explained in the paper. Enter the GEE asset ids of your study region and forest mask, and specify the value of forest types in the forest mask. Click the "load data" button to add a layer of study region, and "load forest mask" to add a layer of forest mask. 
   - CCDC_SMA_basic_app:
   - Display_products_app:
   - Time_series_plotter:
2. codes
   - CCDC_SMA_advanced
   - CCDC_SMA_basic 
3. utilities
   - ut_CCDC_SMA: functions to retrive CCDC-SMA coefficients. 
   - ut_plotter_search: functions used in the time series plotter
   - ut_workflow: functions functions used to run the CCDC-SMA and classify segments.







