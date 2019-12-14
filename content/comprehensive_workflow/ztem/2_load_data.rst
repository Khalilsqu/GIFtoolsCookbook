.. _comprehensive_workflow_ztem_2:


Transforming Field Data into GIF Convention
===========================================


Download Files
--------------

In general, you will start with some topography data and XYZ formatted file.


    - `Download the demo <https://github.com/ubcgif/GIFtoolsCookbook/raw/master/assets/AtoZ_e3dmt_4Download.zip>`_
    - Open GIFtools
    - :ref:`Set the working directory <projSetWorkDir>`


.. important:: Requires GIFtools v2.30 or later.


Import Files
------------

    - :ref:`Import ZTEM data from Geosoft XYZ <importXYZemData>`. The data file is named *ZTEMdata_XYZ.dat* and is in the *assets* folder.

        - There are two frequencies (60 Hz and 360 Hz)
        - There are 4 data groups (TZXR, TZXI, TZYR, TZYI)

    - Once loaded, make sure to :ref:`set IO headers <objectSetioHeaders>` for all MT and ZTEM data.

    - **Pro tip:** To avoid confusion between location and data coordinate systems, use the :ref:`set data headers <objectDataHeaders>` tool to define location columns as *Easting, Northing* and *Elevation*.



Examining the data
------------------


