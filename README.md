# Monitoring Forest Degradation on Google Earth Engine Using Landsat Time Series Analysis

# CCDC-SMA Guidance

### *🎉 News (03/07/2022):*
#### *1. Now you can run CCDC-SMA by grid! Use "Create_grid" to create a grid and use the scripts ended with "by_grid" under the folder named "codes".*
#### *2. A tropics version of CCDC-SMA is now available! See the scripts under the folder named "Tropics/Collection1".*
#### *3. Now you can change the threshold of detecting forest degradation in the apps and codes for all versions!*
#### *4. CCDC-SMA using Landsat collection2 will be available soon.*

Author: Shijuan Chen     
Date: 02/23/2022

This is a guideline of monitoring forest degradation using the Continuous Change Detection and Classification - Spectral Mixture Analysis (CCDC-SMA) algorithm, visualizing the time series of CCDC-SMA model fits and displaying forest degradation products on Google Earth Engine (GEE), explained in Chen et al., 2021. 

Please click the link below to get access to the GEE repository to run CCDC-SMA (See the "Reader" section under the "Script" tab):<br /> 
https://code.earthengine.google.com/?accept_repo=users/shijuanchen32/forest_degradation_georgia

(If you are not a GEE user and interested in the apps, please visit: https://shijuanchen32.users.earthengine.app/)

Please cite the code as: [Chen, S., Woodcock, C.E., Bullock, E.L., Arévalo, P., Torchinava, P., Peng, S. and Olofsson, P., 2021. Monitoring temperate forest degradation on Google Earth Engine using Landsat time series analysis. Remote Sensing of Environment, 265, p.112648.](https://www.sciencedirect.com/science/article/pii/S0034425721003680) 

Please email me at shijuan@bu.edu to request a pdf copy of the full text if you don't have access to Elsevier. 

The GEE repository includes three parts, apps, codes and utilities. There will be different versions of CCDC-SMA for temperate forest and tropical forest, 
and using Landsat Collection 1 and Collection 2. Currently, it is avaliable for temperate forest using Collection 1 (Under folder "Temperate/Collection1"). 

## 1. apps
  - **CCDC_SMA_advanced_app**: ![Image of CCDC_SMA_advanced_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/CCDC_SMA_temperate_advanced.png) This app runs the CCDC-SMA model (advanced version). The advanced version uses different indices and thresholds for different types of forests, explained in the paper. To run this app:
      - Enter the GEE asset ids of your study region and forest mask, and specify the value of forest types in the forest mask. Click the "load data" button to add a layer of study region, and "load forest mask" to add a layer of different forest types. 
      - Specify the start and end year of your study period, and the start and end day (in Julian dates) of a year to run analysis. 
      - Check the boxes to export the results as assets in GEE. The default setting would only export the first year of disturbance, since the full segment results will take longer to export.
      - Click "Run CCDC-SMA" to create an export task in the Code Editor Tasks tab. Click the Run button next to the task to start it. 
      - After the task is finished, enter the GEE asset id of the disturbance year and click "view year of change" to display.
   - **CCDC_SMA_basic_app**: ![CCDC_SMA_basic_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/CCDC_SMA_temperate_basic.png) This app runs the CCDC-SMA model (basic version). To run the basic version, you only need a forest mask and classification of different forest types is not required. To run this app:
     - Enter the GEE asset ids of your study region and forest mask. Click the "load data" buttons to add the inputs.
     - Specify the timing in the settings.
     - Similar to the advanced version, run CCDC-SMA, export and view the results. 
   - **CCDC_SMA_tropic_app**: ![CCDC_SMA_basic_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/CCDC-SMA_basic_version.png) This app runs the CCDC-SMA model (tropic version). To run the tropic version, you only need a forest mask and classification of different forest types is not required. To run this app:
     - Similar to the basic version and advanced version, run CCDC-SMA, export and view the results. 
     - Since gradual degradation is rare in the tropics as vegetation recovers fast, the otuput only include the year of the abrupt change. 
   - **Display_products_app**: ![Display_products_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/display_products.png) This app displays the products of forest degradation, deforestation and land cover. 
     - Click the "Display" buttons to display each product. For annual product, select a year to display.
   - **Time_series_plotter**: ![Time_series_plotter](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/display_ts_CCDC_SMA.png)
   ![Time_series_plotter](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/display_ts_CCDC_SMA_an.png) This app shows the Landsat time series and CCDC-SMA model fits. To run the app:
     - Specify the start and end date in YYYY-MM-DD format, and the start and end day of a year in the analysis.
     - Select an index to display. NDFI and the fraction of endmembers will be used to run the CCDC-SMA model, but only the time series of the selected index will show up in the time series plot. 
     - Click a point on the map to display the time series and model fits. 
     - Click a point on the time series to add the natural-looking Landsat image of this point.
     - You can also explore the pre-loaded four examples of forest degradation. In the search box, enter the id of examples (id ranges from 1 to 4). Click the red point on the map to display the time series of the examples.  
     - Use "Reset" button to reset the map panel.
## 2. codes
   - **CCDC_SMA_advanced**: This script allows users to run CCDC-SMA (advanced) directly without using the apps. The algorithm is the same with the one used in the apps.
   - **CCDC_SMA_advanced_by_grid**: This script allows users to run CCDC-SMA (advanced) by grid. Use the script named "Creat_grid" to create grid first and then run this script. It is recommended to run CCDC-SMA by grid if your region is too large. 
   - **CCDC_SMA_basic**: This script allows users to run CCDC-SMA (basic) directly without using the apps. The algorithm is the same with the one used in the apps.
   - **CCDC_SMA_basic_by_grid**: This script allows users to run CCDC-SMA (basic) by grid. Use the script named "Creat_grid" to create grid first and then run this script. It is recommended to run CCDC-SMA by grid if your region is too large. 
   - **CCDC_run**: This is an example script to run CCDC (with the original) by grid. You can also change the "saveRegion" to a region. To be able to run this code, you will need to use your own grid or region. You can use the script "Create_grid" to create grids.
   - **CCDC_land_cover_classification**: This is an example script of using training data and CCDC coefficients to create land cover maps. To run the code, you will need to use the CCDC assets from "CCDC_run".
   - **Create_grid**: This script allows users to break a study region by grid. You can use the grids created from this script to run CCDC-SMA by grid. 
## 3. utilities
   - **ut_CCDC_SMA**: functions to retrieve CCDC-SMA coefficients. 
   - **ut_plotter_search**: functions used in the time series plotter
   - **ut_workflow**: functions used to run the CCDC-SMA and classify segments.







