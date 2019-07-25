.. _objectEMdtype:

.. include:: <isonum.txt>

EM Data Menu
============



EMsounding
^^^^^^^^^^

For FEM and TEM soundings (for use in the 1D codes), the receiver locations are set **relative to the transmitter locations**. The following parameters are set:

.. _objectEMdtype_EM1Dsounding:

1Dsounding
----------

	- **Receiver:** The dipole moment is set in units :math:`Am^2`
	- **Normal angle from vertical:** Can be defined as a constant value in degrees (0 implies vertical dipole moment) or it can be specified by a data column
	- **Azimuth angle from North:** Clockwise angle in degrees for the dipole moment. Can be set as a constant value or from a data column. Can be set relative to North or relative to the along-line bearing
	- **Bearing:** Bearing sets azimuth angle for the survey in-line direction. If this angle does not exist in a data column, it can be calculate automatically
	- **Along-line offset:** The along-line position of receivers, **relative to transmitter locations**
	- **Cross-line offset:** The cross-line position of receivers, **relative to transmitter locations**
	- **Vertical offset:** The vertical location of the receivers relative to the surface


.. _objectEMdtype_EM3Dsounding:

3Dsounding
----------



.. _objectEMdtype_EMdata:

EMdata
^^^^^^



.. _objectEMaddTx:

Add Transmitters
----------------

GIF formatted FEM (link) and TEM (link) contain all necessary information pertaining to the transmitters and receivers. However, XYZ formatted FEM and TEM data do not (links). Here, the user may specify the transmitter locations and properties based on the data locations for XYZ and CSV formatted data.

Select the object and the menu **"data type menu"** |rarr| **Add transmitters**


.. figure:: ../../../../images/object/data/em/addTransmitters.png
    :align: center
    :width: 400

    An example of the fields for airborne FEM circular loop transmitters


.. important:: Make sure you have :ref:`set i/o headers<objectSetioHeaders>` for the xyz-data locations. This functionality computes the transmitter locations based on the i/o headers.


.. _objectEMaddRx:

Add Receivers
-------------

GIF formatted FEM (link) and TEM (link) contain all necessary information pertaining to the transmitters and receivers. However, XYZ formatted FEM and TEM data do not (links). Here, the user may specify the receiver locations and properties based on the data locations for XYZ and CSV formatted data.

Select the object and the menu **"data type menu"** |rarr| **Add receivers**

**Requirement:** Transmitters must be set


.. figure:: ../../../../images/object/data/em/addReceivers.png
    :align: center
    :width: 400

    An example of the fields for airborne FEM circular loop receivers



.. _objectEMremoveTx:

Remove Transmitters
-------------------

This functionality allows the user to remove transmitter information from the data object.

Select the object and the menu **"data type menu"** |rarr| **Remove transmitters**




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


