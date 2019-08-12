.. _importEMdata:

.. include:: <isonum.txt>

Import EM data
^^^^^^^^^^^^^^


.. toctree::
    :maxdepth: 1

    importFEMdata
    importTEMdata
    importNSEMdata


.. _importXYZemData:

Import XYZ EM data
^^^^^^^^^^^^^^^^^^

Both FEM and TEM data can loaded from a general column file that contains position and multiple data channels.

.. figure:: ../../../../images/importFEM_other.png
    :align: center
    :width: 700


.. note::   - It is recommended to load the raw data as :ref:`FEM3Dsounding <objectEMdtype_EM3Dsounding>` or :ref:`TEM3Dsounding <objectEMdtype_EM3Dsounding>` object such that both transmitters and receivers can be defined at every location using :ref:`Create offset Tx/Rx <objectEMaddTx>`.
            - For detailed instructions on how to import TEM data from a csv or xyz file, follow the instructions in :ref:`this recipe <importVTEMdata>`.
            - XYZ and CSV file formats do not include transmitters, which will need to be imported separately.


**Step 1: assign spatial data, specify frequencies/times and number of data type**

Click this button to specify the Easting, Northing and Elevation columns. The user will also specify the frequencies/times contained within the data and the number of data groups. If the data contain both real and imaginary components of the response at three different frequencies, then there are 3 frequencies and 2 data groups resulting in 6 total data columns.

**Step 2: specify data types**

Select which data type you would like to specify from the drop-down menu and click **specify type**. In the window that pops up, set the header name for the data type and assign the data to each frequency.

**Step 3: add miscellaneous data**

This step is used to define any remaining data columns. This might include orientation information for the transmitters and receivers, etc...

