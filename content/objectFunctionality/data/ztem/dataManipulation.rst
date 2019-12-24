.. _objectDataManipulationZTEM:

.. include:: <isonum.txt>

ZTE==M Data Manipulation Menu
=========================

.. _objectDataManipulationZTEM_transform:

Transform Data Convention for ZTEM Data
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This functionality either:

    - generates apparent resistivity and phase data from impedance data, or
    - generates impedance data from apparent resistivity and phase data

This functionality can be accessed through:

    - **Data manipulation** |rarr| **Create new item** |rarr| **Convert to apparent resistivity and phase data (APPdata)**
    - **Data manipulation** |rarr| **Create new item** |rarr| **Convert to impedance data (IMPdata)**

Some things to note about this functionality:

    - A new data object is created when this functionality is used
    - To compute :math:`\rho_{xy}` and :math:`\phi_{xy}` from Re[ :math:`\! Z_{xy} \!` ] and Im[ :math:`\! Z_{xy} \!` ], you must set the associated data headers. Some goes for the reverse operation.
    - This functionality works regardless of whether data use a time-dependency of :math:`e^{i\omega t}` or :math:`e^{-i\omega t}`.

