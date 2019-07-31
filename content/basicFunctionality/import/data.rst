.. _importData:

.. include:: <isonum.txt>

Import Data
===========

Under **Import** |rarr| **Data**, the user can import various types of geophysical, geological and geographical data from a multitude of file formats. In GIFtools, this results in the creation of a 'data object'. Once created, GIFtools will allow the user to carry out a set of object-dependent actions (or methods) involving the data object. The methods applicable to each data object are presented on the :ref:`object-dependent functionality <objectFunctionalityData>` page. The following data types can be imported into GIFtools:

    - :ref:`Magnetics Data <importMagData>`
    - :ref:`Gravity Data <importGravData>`
    - :ref:`Gravity Gradiometry Data <importGGData>`
    - :ref:`Topography <importTopo>`
    - :ref:`Surface <importSurface>`
    - :ref:`Borehole Data <importBoreholeData>`
    - :ref:`Miscellaneous Property data <importProp>`
    - :ref:`2D DCIP Data <importDCIP2Ddata>`
    - :ref:`3D DCIP Data <importDCIP3Ddata>`
    - :ref:`Frequency-Domain EM Data <importFemData>`
    - :ref:`Time-Domain EM Data <importTemData>`
    - :ref:`Natural Source EM Data (MT and ZTEM) <importNSEMData>`

.. _importMagData:

Import magnetic data
--------------------

Use the main project menu: **Import** |rarr| **Data** |rarr| **Magnetics**

.. figure:: ../../../images/loadMagGen.png
    :align: center
    :width: 400


**File formats:**

Magnetic data can be loaded from three main file types:

    - :ref:`GIF format <magfile>`
    - :ref:`XYZ format <XYZfile>`
    - :ref:`CSV format <CSVfile>`


.. _importGravData:

Import gravity data
-------------------

Use the main project menu: **Import** |rarr| **Data** |rarr| **Gravity**

.. figure:: ../../../images/loadGravGen.png
    :align: center
    :width: 400


**File formats:**

Gravity data can be imported in from three main file types:

    - :ref:`GIF format <gravfile>`
    - :ref:`XYZ format <XYZfile>`
    - :ref:`CSV format <CSVfile>`

.. _importGGData:

Import gravity gradiometry data
-------------------------------

Use the main project menu: **Import** |rarr| **Data** |rarr| **Gravity gradient (GG)**

.. figure:: ../../../images/importgg.png
    :align: center
    :width: 400


**File formats:**

Gravity gradiometry data can be imported in from three main file types:

    - :ref:`GIF format <ggfile>`
    - :ref:`XYZ format <XYZfile>`
    - :ref:`CSV format <CSVfile>`

.. _importTopo:

Import topography
-----------------

Use the main project menu: **Import** |rarr| **Topo**

.. figure:: ../../../images/importTopo.png
    :align: center
    :width: 400

**File formats:**

Topography can be imported through six different file formats:

    - :ref:`3D GIF format <topoGIF3Dfile>`
    - :ref:`2D GIF format <topoGIF2Dfile>`
    - :ref:`XYZ format <XYZfile>`
    - :ref:`CSV format <CSVfile>`
    - Canadian Digital Elevation Data (CDED)
    - USGS 1-degree

.. _importSurface:

Import a surface
----------------

Use the main project menu: **Import** |rarr| **Surface**

.. figure:: ../../../images/importSurface.png
    :align: center
    :width: 400

**File formats:**

Topography from surface can be imported through three different file formats:

    - :ref:`GIF format <topoGIF3Dfile>` (Same as topography)
    - :ref:`XYZ format <XYZfile>`
    - :ref:`CSV format <CSVfile>`


.. _importBoreholeData:

Import borehole data
--------------------

Importing borehole data requires two or three files (survey optional and assumes vertical boreholes if not given) that will be asked for in a separate dialog. To get to the import dialog, use the main project menu: **Import** |rarr| **Borehole Data**

.. figure:: ../../../images/importBoreholeData.png
    :align: center
    :figwidth: 100%

This brings up the following import dialog:

.. figure:: ../../../images/importBHdata/import.png
    :align: center
    :figwidth: 75%

From the browse buttons in Step 1, select the :ref:`collar file <bhCollarfile>`, :ref:`survey file <bhSurveyfile>` (optional; if not provided, GIFtools assumes the borehole extend vertically downwards), and the :ref:`property file <bhPropfile>`. Once all the files are selected in Step 1, click on the "Load" button in Step 2.

For the example files we are using, our import dialog now looks like the following:

.. figure:: ../../../images/importBHdata/import2.png
    :align: center
    :figwidth: 75%

Our example has three properties: ID, LENGTH, and unitless. These are the headers provided in the :ref:`property file <bhPropfile>`. We select all three properties in this case. Once the desired properties are selected, we can move onto Step 3.

Step provides two options on how the borehole data are discretized: either the files contain data points at discrete xyz locations or the files provide a "to" and "from" value for each measurement or observation. Below, we will show how to import each type of borehole data.

.. note:: The datasets used for "discrete" and "interpolate" are different so the property headers will differ as well.

**Discrete**

For discrete data, select the "Discrete" radio button. The import dialog will look like:

.. figure:: ../../../images/importBHdata/import3.png
    :align: center
    :figwidth: 75%

Click OK to import the borehole data. You will notice that a grayed-out BOREdata item has been added to the GIFtools project tree. And the following dialog appears:

.. figure:: ../../../images/importBHdata/headers.png
    :align: center
    :figwidth: 75%

For the collar, survey, and property files, select the appropriate headers from the drop-down menus for each item. The options will match the headers given in the respective files. Once done, the dialog looks like the following:

.. figure:: ../../../images/importBHdata/headers2.png
    :align: center
    :figwidth: 75%

Again, because the borehole data in this case are data points are discrete locations, we use the "Depth" radio button instead of "Intervals". Once all the headers are assigned, click OK. The data are now being imported into GIFtools. Once done, the BOREdata item in the project tree will have a name. The name will be the same as the property file name (in our case, "geology").

The info panel will show the origin of the property data, a data summary, the set i/o headers, and the borehole IDs that were imported:

.. figure:: ../../../images/importBHdata/tree.png
    :align: center
    :figwidth: 100%

Now the borehole data can be visualized, discretized onto a mesh, and used within Model Builder to create models and weighting functions.

.. example:: Collar, survey, and property file along with a GIFtools project to repeat the above steps to import discrete borehole data: `download <https://www.eoas.ubc.ca/~sdevries/GIFtoolsExamples/ImportDiscreteBoreholeData_Example.zip>`__

**Interpolate**

Now, let's import borehole data that has measurement between two elevations (i.e., to and from). Repeat the steps above to import borehole data in GIFtools, up to Step 3. Because this borehole data has "To" and "From" columns, we now select the "Interpolate" radio button in Step 3 for the data discretization.

.. figure:: ../../../images/importBHdata/import4.png
    :align: center
    :figwidth: 75%

We have decided to interpolate these data every 10 m.

Click OK to import the files and move onto the header dialog. The header dialog will appear just as before, except now the "Intervals" option is selected instead of "Depth". Select the appropriate headers for each item. Once done, our dialog looks like the following:

.. figure:: ../../../images/importBHdata/headers3.png
    :align: center
    :figwidth: 75%

Click OK to import and set the headers. Once imported, a BOREdata item has been added to the GIFtools project tree and the name of it is the same as the property file name. In this case, that is "Geology1". When the item is highlighted in the tree, the info panel will provide the same type of information as we saw earlier for the discrete example:

.. figure:: ../../../images/importBHdata/tree2.png
    :align: center
    :figwidth: 100%

Now the borehole data can be visualized, discretized onto a mesh, and used within Model Builder to create models and weighting functions.

.. example:: Collar, survey, and property file along with a GIFtools project to repeat the above steps to import interpolated borehole data: `download <https://www.eoas.ubc.ca/~sdevries/GIFtoolsExamples/ImportDiscreteBoreholeData_Example2.zip>`__

.. note:: GIFtools needs all location data to be in meters! Check your borehole data in case it may be in feet.

**File formats:**

See below links for specifics on the files associated with borehole data:

    - :ref:`Collar file <bhCollarfile>`
    - :ref:`Survey file <bhSurveyfile>`
    - :ref:`Property file <bhPropfile>`


.. _importProp:

Import miscellaneous property data
----------------------------------

This type of data covers the range of anything someone would want to bring in that has a position and value (numeric or character).

Use the main project menu: **Import** |rarr|  **Miscellaneous property data**

.. figure:: ../../../images/importPropData.png
    :align: center
    :width: 400

**File formats:**

Property data is imported via the following file formats:

    - :ref:`XYZ <XYZfile>`
    - :ref:`CSV <XYZfile>`


Import DC/IP data
-----------------

.. _importDCIP2Ddata:

Import DC/IP 2D data
^^^^^^^^^^^^^^^^^^^^

Use the main project menu: **Import** |rarr| **DC/IP** |rarr| **2D**

.. figure:: ../../../images/importDCIP2Ddata.png
    :align: center
    :width: 400


**Note**: Importation from a CSV/XYZ file is found under **Import** |rarr| **DC/IP** and is independent of dimension in the menu

**File formats:**

DC/IP 2D data can be imported via:

    - :ref:`2D GIF file <dcip2dObsfile>`
    - :ref:`XYZ file <XYZfile>`
    - :ref:`CSV file <CSVfile>`


.. _importDCIP3Ddata:

Import DC/IP 3D data
--------------------

Use the main project menu: **Import** |rarr| **DC/IP** |rarr| **3D**

.. figure:: ../../../images/importDCIP3Ddata.png
    :align: center
    :width: 400

**Note**: Importation from a CSV/XYZ file is found under **Import** |rarr| **DC/IP** and is independent of dimension in the menu


**File formats:**

DC/IP 3D data can be imported via:

    - :ref:`3D GIF <dcip3dfile>`
    - :ref:`DCIPF3D <dcip3dfile>`
    - :ref:`XYZ file <XYZfile>`
    - :ref:`CSV file <CSVfile>`


.. _importFemData:

Import GIF FEM data
-------------------

To import Frequency-domain electromagnetic (FEM) data, use the main project
menu:

**Import** |rarr| **Data** |rarr| **Frequency-domain EM**

.. figure:: ../../../images/importFEMdata.png
    :align: center
    :scale: 60%

There are three types of FEM data that can be loaded from files:

    - :ref:`EM1DFM format <importEM1DFMdata>`
    - :ref:`E3Dv1 format <importE3Dv1data>`
    - :ref:`E3Dv2 format <importE3Dv1data>`


.. _importEM1DFMdata:

EM1DFM format
^^^^^^^^^^^^^

**Import** |rarr| **Data** |rarr| **Frequency-domain EM** |rarr| **GIF EM1D format**

Loads a data file for the :ref:`EM1DFM inversion
<invEditOptions_em1dfm>` and forward modeling codes. The data position is set
relative to the transmitter as specified by the `EM1DFM file format
<https://em1dfm.readthedocs.io/en/latest/content/files/supporting.html#observation-file>`_.
The function returns a :ref:`FEM1Dsounding <objectEMdtype_FEM1Dsounding>` object.
The following parameters are set for the user:

    - **Transmitters:**
        - **Dipole moment:** Set by argument
        - **Orientation** Set by argument
        - **Along-line offset (m) =** 0
        - **Cross-line offset (m) =** 0
        - **Vertical offset (m):** Relative to topography

    - **Receiver:**
        - **Dipole moment:** Set by argument
        - **Along-line offset:** The along-line position of receivers, **relative to transmitter locations**
        - **Cross-line offset:** The cross-line position of receivers, **relative to transmitter locations**
        - **Vertical offset:** Relative to topography

.. note:: The position of the data is set by the "sounding" location. Only the relative offsets between the transmitters and receivers are available in the EM1DFM format. Data locations have been assigned to the transmitter locations upon import for consistency.


.. _importE3Dv1data:

E3Dv1 format
^^^^^^^^^^^^

**Import** |rarr| **Data** |rarr| **Frequency-domain EM** |rarr| **GIF E3D format**

Loads data files formated for the original `E3Dv1 data file format <https://e3d.readthedocs.io/en/e3dinv/content/files/obsFile.html#observations-file>`_ .
The function returns a :ref:`FEMdata <objectEMdtype_FEMdata>` object where only the transmitter geometry is defined. The receivers are defined as point measurements that samples the fields (E, H) along the Cartesian axes.

.. note:: The :ref:`FEMdata <objectEMdtype_FEMdata>` object assumes that the provided field data have been measured along the Cartesian axes or that the user has rotated the fields in pre-processing. For more general cases with arbitrary orientation, consider making use of the :ref:`FEMsounding <objectEMdtype_FEMsounding>` class.


.. _importE3Dv2data:

E3Dv2 format
^^^^^^^^^^^^

**Import** |rarr| **Data** |rarr| **Frequency-domain EM** |rarr| **GIF E3Dv2 format**

.. figure:: ../../../images/importFEM_E3Dv2.png
    :align: center
    :scale: 60%

Loads data used by the latest `E3Dv2 inversion code
<https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/index.html#e3d-version-2-tiled-package>`_.
The function returns a :ref:`FEM3Dsounding <objectEMdtype_FEM3Dsounding>` object.
The receivers and transmitters are defined by their respective input files.

    - `Data file <https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/content/files/obsFile.html#observations-file>`_
    - `Frequency file <https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/content/files/freqFile.html#frequencies-file>`_
    - `Receiver file <https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/content/files/receiverFile.html#transmitter-and-receiver-files>`_
    - `Transmitter file <https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/content/files/receiverFile.html#transmitter-and-receiver-files>`_

.. note:: Both the transmitters and receivers geometry are defined in 3D. The relative offsets can be calculated using the :ref:`Calculate Transmitter/Receiver separation <calculateTxRxSeperation>` function.


.. _importTemData:

Import GIF TEM data
-------------------

To import Time-domain ElectroMagnetic (TEM) data, use the main project menu:

**Import** |rarr| **Data** |rarr| **Time-domain EM**

.. figure:: ../../../images/importTEMdata/importTEMdata.png
    :align: center
    :scale: 75%


There are three types of FEM data that can be loaded from files:

    - :ref:`EM1DTM format <importEM1DTMdata>`
    - :ref:`H3DTD | TDoctree v1 format <importTDoctreeV1data>`
    - :ref:`TDoctree v2 format <importTDoctreeV2data>`


.. _importEM1DTMdata:

EM1DTM format
^^^^^^^^^^^^^

**Import** |rarr| **Data** |rarr| **Frequency-domain EM** |rarr| **GIF EM1D format**

Loads a data file for the :ref:`EM1DTM inversion
<invEditOptions_em1dtm>` and forward modeling codes. The data position is set
relative to the transmitter as specified by the `EM1DTM file format
<https://em1dtm.readthedocs.io/en/latest/content/files/supporting.html#observation-file>`_.
The function returns a :ref:`TEM1Dsounding <objectEMdtype_TEM1Dsounding>` object.
The following parameters are set for the user:

    - **Transmitters:**
        - **Dipole moment:** Set by argument
        - **Orientation** Set by argument
        - **Along-line offset (m) =** 0
        - **Cross-line offset (m) =** 0
        - **Vertical offset (m):** Relative to topography

    - **Receiver:**
        - **Dipole moment:** Set by argument
        - **Along-line offset:** The along-line position of receivers, **relative to transmitter locations**
        - **Cross-line offset:** The cross-line position of receivers, **relative to transmitter locations**
        - **Vertical offset:** Relative to topography

.. note:: The position of the data is set by the "sounding" location. Only the relative offsets between the transmitters and receivers are available in the EM1DFM format. Data locations have been assigned to the transmitter locations upon import for consistency.


.. _importTDoctreeV1data:

H3DTD | TDoctree v1 format
^^^^^^^^^^^^^^^^^^^^^^^^^^

**Import** |rarr| **Data** |rarr| **Time-domain EM** |rarr| **GIF H3DTD | TDoctree v1 format**

Loads data files formated for the original `H3DTD data file format <https://e3d.readthedocs.io/en/e3dinv/content/files/obsFile.html#observations-file>`_ .
The function returns a :ref:`TEMdata <objectEMdtype_TEMdata>` object where only the transmitter geometry is defined. The receivers are defined as point measurements that samples the fields (E, H) along the Cartesian axes.

.. note:: The :ref:`TEMdata <objectEMdtype_TEMdata>` object assumes that the provided field data have been measured along the Cartesian axes or that the user has rotated the fields in pre-processing. For more general cases with arbitrary orientation, consider making use of the :ref:`FEMsounding <objectEMdtype_FEMsounding>` class.


.. _importTDoctreeV2data:

TDoctree v2 format
^^^^^^^^^^^^^^^^^^

**Import** |rarr| **Data** |rarr| **Time-domain EM** |rarr| **GIF TDoctree v2 format**

.. figure:: ../../../images/importFEM_E3Dv2.png
    :align: center
    :scale: 60%

Loads data used by the latest `TDoctree v2 inversion code
<https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/index.html#e3d-version-2-tiled-package>`_.
The function returns a :ref:`TEM3Dsounding <objectEMdtype_TEM3Dsounding>` object.
The receivers and transmitters are defined by their respective input files.

    - `Data file <https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/content/files/obsFile.html#observations-file>`_
    - `Frequency file <https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/content/files/freqFile.html#frequencies-file>`_
    - `Receiver file <https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/content/files/receiverFile.html#transmitter-and-receiver-files>`_
    - `Transmitter file <https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/content/files/receiverFile.html#transmitter-and-receiver-files>`_

.. note:: Both the transmitters and receivers geometry are defined in 3D. The relative offsets can be calculated using the :ref:`Calculate Transmitter/Receiver separation <calculateTxRxSeperation>` function.


.. _importXYZemData:

Import XYZ EM data
^^^^^^^^^^^^^^^^^^

Both FEM and TEM data can loaded from a general column file that contains position and multiple data channels.

.. figure:: ../../../images/importFEM_other.png
    :align: center
    :width: 700


.. note:: It is recommended to load the raw data as :ref:`FEM3Dsounding <objectEMdtype_FEM3Dsounding>` or :ref:`TEM3Dsounding <objectEMdtype_TEM3Dsounding>` object such that both transmitters and receivers can be defined at every location using :ref:`Create offset Tx/Rx <objectEMaddTx>`.

**NOTE**: For detailed instructions on how to import TEM data from a csv or xyz file, follow the instructions in :ref:`this recipe <importVTEMdata>`.

**NOTE**: XYZ and CSV file formats do not include transmitters, which will need to be imported separately.


**Step 1: assign spatial data, specify frequencies/times and number of data type**

Click this button to specify the Easting, Northing and Elevation columns. The user will also specify the frequencies/times contained within the data and the number of data groups. If the data contain both real and imaginary components of the response at three different frequencies, then there are 3 frequencies and 2 data groups resulting in 6 total data columns.

**Step 2: specify data types**

Select which data type you would like to specify from the drop-down menu and click **specify type**. In the window that pops up, set the header name for the data type and assign the data to each frequency.

**Step 3: add miscellaneous data**

This step is used to define any remaining data columns. This might include orientation information for the transmitters and receivers, etc...



.. _importNSEMData:

Import natural-source EM data
-----------------------------

There are a few file options to import magnetotelluric (MT: impedance or apparent resistivity and phase) or Z-axis Tipper EM (ZTEM) data. They include:

    - :ref:`MTZ3D <importNSEMData_mtz3d>` formatted data
    - :ref:`E3DMT version 1 <importNSEMData_e3dmt1>` formatted data
    - :ref:`E3DMT version 2 <importNSEMData_e3dmt2>` formatted data
    - :ref:`EDI <importNSEMData_edi>` formatted MT data
    - :ref:`ASCII <importNSEMData_ascii>` formatted ZTEM data


MT or ZTEM data: GIF format
^^^^^^^^^^^^^^^^^^^^^^^^^^^

To load MT data that are in a GIF-formatted structure, the menu structure is:

**Import** |rarr| **Data** |rarr| **Natural-source EM** |rarr| **MT / ZTEM: GIF format** |rarr| **"Data type"**

.. figure:: ../../../images/importMTGif.png
    :align: center
    :width: 400

.. _importNSEMData_mtz3d:

MTZ3D data
~~~~~~~~~~

.. raw:: html
    :file: ../../../underconstruction.html


.. _importNSEMData_e3dmt1:

E3DMT version 1 data
~~~~~~~~~~~~~~~~~~~~

`Observed/locations <https://e3dmt.readthedocs.io/en/manual_ver1/content/files/obsFile.html>`__ data and `predicted <https://e3dmt.readthedocs.io/en/manual_ver1/content/files/preFile.html>`__ data can be loaded from:

    - **Import** |rarr| **Data** |rarr| **Natural-source EM** |rarr| **MT / ZTEM: GIF format** |rarr| **E3DMT Obeserved/Locations Data (ver 1)**
    - **Import** |rarr| **Data** |rarr| **Natural-source EM** |rarr| **MT / ZTEM: GIF format** |rarr| **E3DMT Predicted Data (ver 1)**

Some things to note about loading E3DMT version 1 observed/locations data:

    - If MT and ZTEM are contained within the same file, GIFtools will parse into an IMPdata object and a ZTEMdata object
    - Although it is good practice, the locations for each frequency do not need to be the same. Frequency-location pairs without data are given a value of NaN.

Some things to note about loading E3DMT version 1 predicted data:

    - The user must specify the ZTEM and or IMP data object(s) associated with the predicted data in the screen shown below. E3DMT version 1 does not support apparent resistiviy and phase data.
    - Let us assume multiple data objects were used to create the observations/locations file for the forward modeling/inversion. When loading the predicted data, the user must select the data objects in the same order they used to create the observations/locations file.


.. figure:: ../../../images/importE3DMTpre1.png
    :align: center
    :width: 400

.. _importNSEMData_e3dmt2:

E3DMT version 2 data
~~~~~~~~~~~~~~~~~~~~

`Observed/locations <https://e3dmt.readthedocs.io/en/manual_ver2/content/files/obsFile.html>`__ data and `predicted <https://e3dmt.readthedocs.io/en/manual_ver2/content/files/preFile.html>`__ data can be loaded from:

    - **Import** |rarr| **Data** |rarr| **Natural-source EM** |rarr| **MT / ZTEM: GIF format** |rarr| **E3DMT Obeserved/Locations Data (ver 2)**
    - **Import** |rarr| **Data** |rarr| **Natural-source EM** |rarr| **MT / ZTEM: GIF format** |rarr| **E3DMT Predicted Data (ver 2)**

Some things to note about loading E3DMT version 2 observed/locations data:

    - The user selects the `Observations <https://e3dmt.readthedocs.io/en/manual_ver2/content/files/obsFile.html>`__ / `survey index file <https://e3dmt.readthedocs.io/en/manual_ver2/content/files/indexFile.html>`__ from the first pop-up window, the `receivers file <https://e3dmt.readthedocs.io/en/manual_ver2/content/files/receiverFile.html>`__ from the second pop-up window, and the `frequencies file <https://e3dmt.readthedocs.io/en/manual_ver2/content/files/freqFile.html>`__ form the third pup-up window.
    - Although it is good practice, the locations for each frequency do not need to match. Frequency-location pairs without data are given a value of NaN.
    - The IDs for the receivers do not need to be in any particular order but they do need to be unique.
    - If the respective IDs for Hx and Hy receivers are all the same (e.g. a base station for ZTEM data), the resulting ZTEM data object will still have a datatype of *MTH*.

Some things to note about loading E3DMT version 2 predicted data:

    - The user must select the associated ZTEM or IMP data object when loading predicted data. E3DMT version 2 does not support apparent resistiviy and phase data.

.. _importNSEMData_edi:

MT data: EDI format
^^^^^^^^^^^^^^^^^^^

To load MT data that are in one or more EDI files (GIFtools will prompt and allow for multiple files), the menu structure is:

    - Make impedance data object: **Import** |rarr| **Data** |rarr| **Natural-source EM** |rarr| **MT EDI file(s)** |rarr| **Impedance**
    - Make apparent resistivity data object: **Import** |rarr| **Data** |rarr| **Natural-source EM** |rarr| **MT EDI file(s)** |rarr| **Apparent resistivity and phase:**

Once selected, the user must do the following:

    1) Use *Browse* to find the EDI file(s) which they would like to important data from
    2) Select *Load* to temporarily load all the data
    3) Select the properties (data columns) which they would like in their final data object (IMPdata or APPdata)
    4) Choose whether or not the data must be transferred from Northing-Easting-Down to Easting-Northing-Up (GIF)
    5) Select *OK*


.. figure:: ../../../images/importEDI.png
    :align: center
    :width: 400

.. important::

    - We assume the EDI file data are defined by `The Society of Exploration Geophysicists MT / EMAP Data Interchange Standard <https://seg.org/Portals/0/SEG/News%20and%20Resources/Technical%20Standards/seg_mt_emap_1987.pdf>`__ . That is, the EDI data uses a :math:`+i\omega t` :ref:`time-dependency <sign_mt_conv>`. Also, the data are Northing-Easting-Down.
    - GIFtools will convert the (LONG, LAT) to WGS84 UTM when importing.
    - GIFtools converts impedance data from a :math:`+i\omega t` (EDI standard) convention to a :math:`-i\omega t` (GIF standard) convention automatically.
    - GIFtools assumes that impedance tensor data have column names *ZXXR, ZXXI, ZXYR, ZXYI, ZYXR, ZYXI, ZYYR* and *ZYYI* and the apparent resistivities have column names *RHOXX, PHSXX, RHOXY, RHOXY, RHOYX, RHOYX, RHOYY* and *RHOYY*.
    - GIFtools assumes the impedance data are in units mV/km/nT and will converted these data to V/A as required by GIF inversion programs.
    - If impedance data are being imported, GIFtools will import all other data columns but will *NOT* modify them in any way. Thus if ZTEM or other data exist in the EDI files, it is up to the user to apply the appropriate corrections upon loading.


.. _importNSEMData_ascii:

ZTEM data: ASCII format
^^^^^^^^^^^^^^^^^^^^^^^
To load ZTEM data that are in a CSV or XYZ ASCII format, the menu structure is:

- XYZ format: **Import** |rarr| **Data** |rarr| **Natural-source EM** |rarr| **ZTEM general ASCII** |rarr| **XYZ**
- CSV format: **Import** |rarr| **Data** |rarr| **Natural-source EM** |rarr| **ZTEM general ASCII** |rarr| **CSV file**

.. figure:: ../../../images/importZTEMascii.png
    :align: center
    :width: 400


**NOTE:** XYZ and CSV file formats do not include base stations for ZTEM data, which will need to be imported or set separately.








