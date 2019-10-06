.. _objectEMDataManipulation:

.. include:: <isonum.txt>

EM Data Manipulation
====================

.. _objectTimeFreqExtract:

Extract data based on times or frequencies
------------------------------------------

To extract all the data associated with a certain time(s) or frequency(ies), click on the data item of interest and use the menu:

- TEM data: **Data manipulation** |rarr| **Time-based extraction of data**

- FEM data: **Data manipulation** |rarr| **Frequency-based extraction of data**


.. figure:: ../../../../images/emDataManMenu.png
    :align: center
    :width: 400


**NOTE:** This will create a new data item.


.. _objectTimeFreqEdit:

View and/or edit the times or frequencies of a data set
-------------------------------------------------------

To view (with the option to edit) the times or frequencies within a data set, click on the data item of interest and use the menu:

- TEM data: **Data manipulation** |rarr| **Change or view times**

- FEM data: **Data manipulation** |rarr| **Change or view frequencies**


.. figure:: ../../../../images/emDataManMenu.png
    :align: center
    :width: 400



**NOTE:** Editing will *NOT* create a new dataset and will over-write the previous times/frequencies.



.. _objectEMsetDataNorm:

Set Data Normalization (FEM and TEMsounding Only)
-------------------------------------------------

Both the EM1DFM and EM1DTM inversion codes can interpret a variety of representations of EM data.
To ensure the data are interpreted correctly by the EM1DFM and EM1DTM codes, the data normalization must be properly set.
This functionality can be accessed through:

**Data manipulation** |rarr| **Set Data Normalization**


.. _objectEMsetDataNorm_FEM:

FEM data
^^^^^^^^

For FEM sounding data, the options for defining the type of data are as follows:

    - **ppm:** secondary field component as parts-per-million of the primary field
    - **%:** secondary field component as a fractional percent of the strength of the primary field
    - **A/m:** secondary field component in A/m
    - **Total field:** total field (primary + secondary) in A/m


.. _objectEMsetDataNorm_TEM:

TEM data
^^^^^^^^

For TEM sounding data, the options for defining **B-field data** are as follows:

    - **nano-Tesla**
    - **micro-Tesla**
    - **milli-Tesla**

and the options for defining **dB/dt data** are as follows:

    - **micro-Volts**
    - **milli-Volts**
    - **Volts**

.. note:: If the dipole moment of the receiver is 1 Am :math:`\! ^2`, then the magnitude of the EMF induced in the receiver coil in Volts equals the time-derivative of the magnetic flux density in T/s.


.. _objectEMsetTimeNorm:

Set Time Normalization (TEMsounding Only)
-----------------------------------------

The EM1DTM inversion code can use a variety of units for the time channel column.
To ensure the data are interpreted correctly by the EM1DTM code, the time normalization must be properly set.
This functionality can be accessed through:

**Data manipulation** |rarr| **Set Time Normalization**

The options for defining the units of the time column are as follows:

    - **micro-seconds**
    - **milli-seconds**
    - **seconds**

.. _calculateTxRxSeperation:

Calculate Transmitter-Receiver seperation
-----------------------------------------

This function computes the in-line, cross-line and vertical seperation between the transmitter and receiver for each datum.


.. _objectEMaddTx:

Add Transmitters
----------------

Here, the user may specify the transmitter locations
and properties based on the data locations.

.. figure:: ../../../../images/object/data/em/addTransmitters.png
    :align: center
    :width: 400


Select the object: **"data type menu"** |rarr| **Add transmitters**

- Transmitter geometry
    - **From File:** Lets the user import a template geometry (XYZ coordinates) defining the transmitter coil.
    - **Loop:** Defines a simple loop transmitter with radius set by the user.
    - **Dipole:** Defines a dipole transmitter with moment set by the user (for EM1Dinversion)
- Bearing
    - **Calculate:**  Let GIFtools determine the bearing of survey lines. Assumes that the survey points are sorted in order of acquisition.
    - **From data object:** Bearing already supplied by the data object.
- Offsets relative to bearing (XYZ)
    - **Along-line offset:** Distance along the survey lines between the data location and transmitter
    - **Cross-line offset:** Distance perpendicular to the survey lines between the data location and transmitter
    - **Vertical offset:** Elevation difference between the data location and transmitter. For the :ref:`EM1Dsounding <objectEMdtype_FEM1Dsounding>` class, the offset is relative to the ground.
- Rotation angles
    - **Relative to bearing:** Apply the rotation angles relative to the flight line orientation. Otherwise angles are relative to the Cartesian grid.
    - **Pitch angle:** Rotation angle about the wings of the bird. Positive angle moves the nose up, tail down.
    - **Roll angle:** Rotation angle about the length of the bird. Positive angle moves the left wing up, right wing down.
    - **Yaw angle:** Rotation angle about the XY plane. Positive angle rotates the bird clockwise.


.. figure:: ../../../../images/object/data/em/PitchRollYaw.png
    :align: center
    :scale: 100%


.. important:: Make sure you have :ref:`set i/o headers<objectSetioHeaders>` for the xyz-data locations. This functionality computes the transmitter locations based on the i/o headers.



.. _objectEMremoveTx:

Remove Transmitters
-------------------

This functionality allows the user to remove transmitter information from the data object.

Select the object and the menu **"data type menu"** |rarr| **Remove transmitters**


.. _objectEMaddRx:

Add Receivers
-------------

See the :ref:`Add Transmitter <objectEMaddTx>` function.


.. _objectEMdtype_FEM1Dsounding:

.. _objectEMwaveform:

Waveform (TDEM objects only)
----------------------------

Here, we describe functionality related to defining, viewing and exporting waveforms for TEM data objects. This functionality is accessed through:

**data type menu** |rarr| **Waveform**


.. _objectEMwaveform_exp:

Create Exponent On - Ramp Off
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Here, the user defines an exponential ramp-on linear ramp-off waveform and sets it to the selected TEM data object. This functionality is accessed through:

**data type menu** |rarr| **Waveform** |rarr| **Create exponent on; ramp off**

The parameters defining this waveform are as follows:

    - **minimum time:** the starting time for the waveform (in seconds). This time **must** be before your first time channel
    - **maximum time:** the end time for the waveform (in seconds). This time **must** be after your latest time channel
    - **time = 0:** the shut-off time
    - **Number of segments:** Number of intervals after t0 which use a different time-step length
    - **Samples per segment:** Number of linearly sampled points which define the time-step length in each segment
    - **Exponent slope:** The constant :math:`\alpha` defining the exponential ramp on
    - **Exponent time:** The duration of the exponential ramp on
    - **Number of exp samples:** Number of data points, linearly sampled, defining the waveform during the exponential ramp on
    - **Ramp time:** The duration of the linear ramp off
    - **Number of ramp samples:** Number of data points, linearly sampled, defining the waveform during the linear ramp off



.. _objectEMwaveform_stepoff:

Create Step Off
^^^^^^^^^^^^^^^

Here, the user defines a step-off waveform and sets it to the selected TEM data object. This functionality is accessed through:

**data type menu** |rarr| **Waveform** |rarr| **Create step off**

The parameters defining this waveform are as follows:

    - **minimum time:** the starting time for the waveform (in seconds). This time **must** be before your first time channel
    - **maximum time:** the end time for the waveform (in seconds). This time **must** be after your latest time channel
    - **time = 0:** the shut-off time
    - **Number of segments:** Number of intervals after t0 which use a different time-step length
    - **Samples per segment:** Number of linearly sampled points which define the time-step length in each segment



.. _objectEMwaveform_import:

Import a Waveform
^^^^^^^^^^^^^^^^^

Here, the user imports a custom waveform from a text file and sets it to the selected TEM data object. This functionality is accessed through:

**data type menu** |rarr| **Waveform** |rarr| **Import (3D format)**


.. _objectEMwaveform_view:

View
^^^^

Here, the user may look at the waveform assigned to the selected TEM data object. This functionality is accessed through:

**data type menu** |rarr| **Waveform** |rarr| **View**

.. _objectEMwaveform_1D:

Export for 1D
^^^^^^^^^^^^^

Here, the user may export the waveform in the format used by the EM1DTM code. This functionality is accessed through:

**data type menu** |rarr| **Waveform** |rarr| **Export for 1D**


.. _objectEMwaveform_3D:

Export for 3D
^^^^^^^^^^^^^

Here, the user may export the waveform in the format used by 3D codes. This functionality is accessed through:

**data type menu** |rarr| **Waveform** |rarr| **Export for 3D**


