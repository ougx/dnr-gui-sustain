
# Sustainable Use Scenario Tool for Analysis and Informing Nebraskans (*SUSTAIN*) #

![logo](logo.png)

## Main Window ##
The `Main` window is the first window that appears when the application starts. The settings `Baseline Name File` and `Scenario Output Dir` need to be specified to open other windows.

* `Baseline Name File` is the file path of the model master file, which includes the information to run the models.
* `Scenario Output Dir` defines the output directory of the current analysis. All the new model input files output files will be placed in this directory. If the model is completed, *SUSTAIN* will read the model results in this directory.

When the `Main` window starts, it reads a configuration file `config.ini` in the same directory of the application. The configuration file includes the saved settings of `Baseline Name File` and `Scenario Output Dir`.

There are four buttons in the `Main` window. Each button will open a new window with different functions. These windows are introduced as follows.

![Main Window](screenshot/main.png)

When the `Main` window is closed, a dialog window will pop up to provide the option to save the current settings to the configuration file. Though it is not recommended, experienced user can also modify the `config.ini` file using text editing tools.

![SaveConfig](screenshot/SaveConfig.png)

## Watershed Model Data Window ##
The `Watershed Model Data` window shows watershed model data including land use, and groundwater pumping and recharge estimated with the watershed model `CropSim`.

* Data area
  * `Output Zone` allows you to select the spatial division of the data to be plotted. For example, if the *NRD* option is selected, the model results are aggregated in each NRD. The customized zone allows users select an existing zone file or shapefiles to define the output zone. Please see the Customized Zone section.
  * `Show Zones` button activates a new window displaying the distribution map of the selected output zones.
  * `Load Results` button loads the results from the model files and calculate the pumping, recharge and land cover area for each output zone. It can take a while and the program will be frozen during the reading process.
* Selection area: The selection area provide the filtering function on the data. Users can select specific variable, zone, crop type and irrigation type for plotting or export. In each selection block, one or more items can be selected. To select multiple items, press the *Ctrl* when clicking the items or check the boxes. If no item is selected when plotting, the program assumes that all the items are selected (no filtering).
  * `Variables` selection block provides the option of variables to be plotted or exported. Currently, user can select annual groundwater pumping, groundwater recharge or/and land use acres.
  * `Zones` selection block provides the option of zones to be plotted or exported. The items provided in this block will change when the output zone is changed.
  * `Crops` selection block provides the option of crop types to be plotted or exported. The items in this block depends on the crop types used in the waterhsed model and usually include corn, pasture (past), sugar beets, edible beans, alfalfa, winter wheat and soybean.
  * `Irrigation` selection block provides the option of irrigation types to be plotted or exported. There are four irrigation types including dryland (no irrigation), groundwater irrigated, surface water irrigated and commingle irrigated.
* Plot control area: In the plot control area, users can customize the plots using the controls.
  - `Plot type` controls if the data are plotted as lines, bars or areas.
  - `Stacked` checkbox allows users to stack the bar and area plots. Note that the bar and area plots will be stacked based on all other dimensions except the time.
  - `Cumulative` checkbox allows users to plot the cumulative values instead of the annual values.
  - `Agg.Zones` checkbox allows users to aggregate the values based on zones. For example, if the user want to plot the total pumping in Box Butte and Cherry counties, the user can select *Groundwater pumping* and these two counties for data, and check this `Agg.Zones` checkbox.
  - `Agg.Crops` checkbox is similar to `Agg.Zones` but it aggregates over crop types instead of zones.
  - `Agg.IrrTypes` checkbox is similar to `Agg.Zones` but it aggregates over irrigation types instead of zones.
  - `xAxis Label` allows users make change to the title of the x-axis of the plot.
  - `yAxis Label` allows users make change to the title of the y-axis of the plot.
  - `Plot Title` allows users make change to the plot title.
  - `Plot` button allows users make the plot based on the selected data and options.
  - `Export Data` allows users export the plotting data as a spreadsheet. Note that the plotting data can saved only after they are plotted.
* Plotting area: the plotting area is on the right of the window. It includes the plotting figure and the navigation tool bar.
  - `Plotting figure` occupy the most plotting area. When user resize the window, the size of the plotting figure will change accordingly.
  - `Navigation tool bar` is at the bottom of the plotting area. It can be used to control the view of the figure. The detailed usage of each button can be found on this page:  https://matplotlib.org/users/navigation_toolbar.html.

![Watershed](screenshot/Watershed.png)

## Recharge/Pumping Change Window ##
The Recharge/Pumping Change (RPC) Window provides a very versatile tool to change the groundwater recharge and pumping through the WELL package of MODFLOW. It can create new MODFLOW input files based on the recharge or pumping changes you make.

* Menu: the menu includes the command buttons that you can used.
  - `Add` button will add the current change to the change table on the right of the window.
  - `Delete` button can used to remove a change row from the change table.
  - `Save` button will transform all the changes in the change table into MODFLOW input files. When all the files are created, user will be asked whether to run the model.
  - `Reset` button will delete all the changes in the change table at once.
  - `Run` will activate the MODFLOW run using the new input files.
  - `Help` will show a description of how to make changes in pumping and recharge.
* Data area
  - `Input Zone` allows users to select what spatial division of recharge/pumping you want to make change with. For example, if the *NRD* option is selected, the changes will be made in the selected NRD areas. The customized zone allows users select an existing zone file or shapefiles to define the input zone. Please see the Customized Zone section.

![Recharge](screenshot/recharge.png)


## Customizaed Zone ##
