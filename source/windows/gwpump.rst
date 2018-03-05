Recharge/Pumping Change
=======================

The Recharge/Pumping Change Window provides a very versatile tool to change the groundwater recharge and pumping through the WELL package of MODFLOW. It can create new MODFLOW input files based on the recharge or pumping changes you make.

* **Menu** includes the command buttons that you can used.

  - ``Add`` add the current change to the change table on the right of the window.
  - ``Delete`` can used to remove a change row from the change table.
  - ``Save`` transform all the changes in the change table into MODFLOW input files. When all the files are created, user will be asked whether to run the model.
  - ``Reset`` delete all the changes in the change table at once.
  - ``Run`` activate the MODFLOW run using the new input files.

  - ``Help`` show a description of how to make changes in pumping and recharge.

* **Data area**

  - ``Input Zone`` select what spatial division of recharge/pumping you want to make change with. For example, if the *NRD* option is selected, the changes will be made in the selected NRD areas. The customized zone allows users select an existing zone file or shapefiles to define the input zone. Please see the Customized Zone section.
  - ``Start Year`` and ``End Year`` specify the years for the change. Please note that the change rate is constant over the selected years for each respective change.
  - ``Month`` filtering block specify the months for the change. The annual change rate will be equally distributed by the numbers of days in the selected months.
  - ``Change existing wells (%)`` modify the pumping rate of each existing wells in the selected zones and time by multiplying the percentage in the textbox next to this checkbox.
  - ``Change existing wells (af/yr)`` modify the pumping rate of each existing wells in the selected zones and time by adding the changing rate in the textbox next to this checkbox. Please note that the changing rate is equally distributed to the numbers of days of the selected months in each selected year.
  - ``Add new wells (af/yr)`` change pumping/recharge by add new wells at each cell in the selected zones. The changing rate specified in the textbox next to this checkbox is equally distributed to the model grid cells in the selected zones and the numbers of days of the selected months in each selected year.

* **Change table** display the changes added by users. Please note that, the changes are made subsequently. Therefore, the later changes will be

.. image:: gwpump.png
