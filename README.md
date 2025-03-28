# Monitoring Forest Degradation on Google Earth Engine Using Landsat Time Series Analysis

# CCDC-SMA Guidance

### *🎉 News (03/11/2025): Fixed a bug in the time series plotter to properly display images when clicking a point in the time series plot.  
#### *Previous updates:*
#### *1. CCDC-SMA using Landsat collection2 (including Landsat 9) is available now!*
#### *2. Now you can run CCDC-SMA by grid if your study area is large!*
#### *3. A tropics version of CCDC-SMA is now available!*
#### *4. Now you can change the threshold and/or change probability of detecting forest degradation in the apps and codes for all versions!*


Author: Shijuan Chen     
Date: 02/23/2022

This is a guideline of monitoring forest degradation using the Continuous Change Detection and Classification - Spectral Mixture Analysis (CCDC-SMA) algorithm, visualizing the time series of CCDC-SMA model fits and displaying forest degradation products on Google Earth Engine (GEE), explained in Chen et al., 2021. 

Please click the link below to get access to the GEE repository of the codes and apps to run CCDC-SMA (See the "Reader" section under the "Script" tab):<br /> 
https://code.earthengine.google.com/?accept_repo=users/shijuanchen32/forest_degradation_georgia

(If you are not a GEE user and interested in the apps, please visit: https://shijuanchen32.users.earthengine.app/)

Please cite the code as: [Chen, S., Woodcock, C.E., Bullock, E.L., Arévalo, P., Torchinava, P., Peng, S. and Olofsson, P., 2021. Monitoring temperate forest degradation on Google Earth Engine using Landsat time series analysis. Remote Sensing of Environment, 265, p.112648.](https://www.sciencedirect.com/science/article/pii/S0034425721003680) 

Please email me at shijuan@bu.edu to request a pdf copy of the full text if you don't have access to Elsevier. 

There are different versions of CCDC-SMA for temperate region (Under the folder named 'Temperate') and tropics (Under the folder named 'Tropics'). Each version has apps and codes to run CCDC-SMA. If your study region is in the boreal forest, you can try either temperate or tropic versions. You can either use the scripts in "Optional" folder to create forest mask and strata or your own forest mask or land cover maps. 

## 1. apps

  - **CCDC_SMA_advanced_app**: ![Image of CCDC_SMA_advanced_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/Temperature_advanced_C2.png) This app runs the CCDC-SMA model (temperate, advanced version). The advanced version uses different indices and thresholds for different types of forests, explained in the paper. To run this app:
      - Enter the GEE asset ids of your study region and forest mask, and specify the value of forest types in the forest mask. Click the "load data" button to add a layer of study region, and "load forest mask" to add a layer of different forest types. 
      - Specify the start and end year of your study period, and the start and end day (in Julian dates) of a year to run analysis. 
      - Check the boxes to export the results as assets in GEE. The default setting would only export the first year of disturbance, since the full segment results will take longer to export.
      - Click "Run CCDC-SMA" to create an export task in the Code Editor Tasks tab. Click the Run button next to the task to start it. 
      - After the task is finished, enter the GEE asset id of the disturbance year and click "view year of change" to display.
      - The full segment results include forest degradation type (1 for gradual only, 2 for abrupt only, and 3 for both), start year of gradual change ("tStart"), end year of gradual change ("tEnd") and year of abrupt change ("tBreak").
     
   - **CCDC_SMA_basic_app**: ![CCDC_SMA_basic_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/Temperature_basic_C2.png) This app runs the CCDC-SMA model (temperate, basic version). To run the basic version, you only need a forest mask and classification of different forest types is not required. To run this app:
     - Enter the GEE asset ids of your study region and forest mask. Click the "load data" buttons to add the inputs.
     - Specify the timing in the settings.
     - Similar to the advanced version, run CCDC-SMA, export and view the results. 
    
   - **CCDC_SMA_tropic_app**: ![CCDC_SMA_basic_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/Tropic_C2.png) This app runs the CCDC-SMA model (tropic version). To run the tropic version, you only need a forest mask and classification of different forest types is not required. To run this app:
     - Similar to the basic version and advanced version, run CCDC-SMA, export and view the results. 
     - Since gradual degradation is rare in the tropics as vegetation recovers fast, the outputs only include the years of the abrupt changes. 
  
   - **Display_products_app**: ![Display_products_app](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/display_product_new.png) This app displays the products of forest degradation, deforestation and land cover. 
     - Click the "Display" buttons to display each product. For annual product, select a year to display.
  
   - **Time_series_plotter**: ![Time_series_plotter](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/display_ts_tropic_new.png)
   ![Time_series_plotter](https://github.com/shijuanchen/forest_degradation_georgia/blob/master/display_ts_temperate_new.png) This app shows the Landsat time series and CCDC-SMA model fits. To run the app:
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
   - **CCDC_SMA_tropic**: This script allows users to run CCDC-SMA (tropic) directly without using the apps. The algorithm is the same with the one used in the apps.
   - **CCDC_SMA_tropic_by_grid**: This script allows users to run CCDC-SMA (tropic) by grid. Use the script named "Creat_grid" to create grid first and then run this script. It is recommended to run CCDC-SMA by grid if your region is too large. 
   - **Create_grid**: This script allows users to break a study region by grid. You can use the grids created from this script to run CCDC-SMA by grid. 


## 3. utilities
   - **ut_CCDC_SMA**: functions to retrieve CCDC-SMA coefficients. 
   - **ut_plotter_search**: functions used in the time series plotter
   - **ut_workflow**: functions used to run the CCDC-SMA and classify segments.

## Supplementary materials:
1. A mini-documentary about monitoring forest degradation in Georgia: https://youtu.be/_cH3hs8zrYI 
2. Lab instruction of CCDC-SMA in GRS EE644/CAS EE 444 - Digital Image Processing class: https://drive.google.com/file/d/1602r0t90nYxB3aHQtKLPhpsmD2-E8QFc/view?usp=sharing . CCDC-SMA has been used in the students final projects in a digital image processing class in these regions: Canada (2), Madagascar (2), India (1) and Peru (1).
3. Ongoing relevant work using CCDC-SMA ![CCDC-SMA](
https://github.com/shijuanchen/forest_degradation_georgia/blob/master/CCDC-SMA.png)
## Acknowledgement: 
  Many thanks to Dr. Eric L. Bullock, Dr. Paulo Arévalo, Dr. Xiaojing Tang for their help!





