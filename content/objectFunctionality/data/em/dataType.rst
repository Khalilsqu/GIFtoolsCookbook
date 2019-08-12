.. _objectEMdtype:

.. include:: <isonum.txt>

EM Data Classes
===============

There are two main types of EM data that can be created in GIFtools.

- :ref:`EMdata <objectEMdtype_EMdata>`
- :ref:`EMsounding <objectEMdtype_EMdata>`

.. _objectEMdtype_EMdata:

EMdata
^^^^^^

For the ``EMdata`` class, the receivers are assumed to be point measurements of EM fields (E, H) collected along
the Cartesian directions. Only the transmitter type can be defined as

- **TRX_LOOP:** Simple loop
	- Radius of the transmitter
	- :math:`\theta` angle from vertical (0=planar loop)
	- :math:`\alpha` (azimuthal) angle from North
- **TRX_ORIG:** Defined by vertices
	- For purely inductive source, the first and last entry must be the same in order to close the wire path.

The ``EMdata`` class is used for:

- `E3Dv1 <https://e3d.readthedocs.io/en/e3dinv/content/files/obsFile.html#observations-file>`_
- `H3DTD <https://gif.eos.ubc.ca/sites/default/files/sdevriese/files/H3DTDinv_manual_v_1_2.pdf>`_
- `TDoctree v1 <https://tdoctree.readthedocs.io/en/tdoctree_ver1/>`_

.. figure:: ../../../../images/object/data/em/EMdata.png
    :align: center
    :scale: 75%


.. _objectEMdtype_EMsounding:

EMsounding
^^^^^^^^^^

For the ``EMsounding`` class, parameters describing both the transmitter and receiver are
required and used in the forward and inverse problems. This is the most
general format. It allows to easily store airborne data collected from
transmitters and receivers of arbitrary shapes and orientations. The
``EMsounding`` is further divided into two sub-classes:


.. _objectEMdtype_EM1Dsounding:

EM1Dsounding
------------

For ``EM1Dsounding`` objects, receiver can either be defined as a ``dipole``
or ``loop`` source. The position of the receiver is set **relative to the
transmitter locations**. The following parameters are required:

	- **Along-line offset:** The along-line position of receivers, **relative to transmitter locations**
	- **Cross-line offset:** The cross-line position of receivers, **relative to transmitter locations**
	- **Vertical offset:** The vertical location of the receivers relative to the surface
	- **Dipole Moment:** Uses a right-handed **positive down** coordinate system

The ``EM1Dsouding`` data class used for:

- `EM1DFM inversion <https://em1dfm.readthedocs.io/en/latest/#em1dfm-package>`_,
- `EM1DTM inversion <https://em1dtm.readthedocs.io/en/latest/#em1dtm-package>`_

.. figure:: ../../../../images/object/data/em/create_FEM_Tx_Rx.png
    :align: center
    :scale: 75%


.. _objectEMdtype_EM3Dsounding:

EM3Dsounding
------------

For ``EM3Dsounding`` objects, information about the position and orientation of
the system are stored directly by the transmitter and receiver objects.

- **Loop transmitter/receiver**: Loop transmitters and receivers must be defined in a left-handed (clockwise) manner. For example, a horizontal loop must be defined in a clockwise manner for its dipole moment to be in the vertical direction. For N loop segments, you will need to define N+1 nodes; e.g. you must close the loop. If a closed loop is used to define a receiver, the corresponding data are the magnetic field in units A/m.
- **Wire transmitter/receiver**: Wire transmitters and receivers are defined using node locations without repetition of the first node.

For display purposes, the averaged receiver node locations are used to plot the data.

This data class is use for:

- `E3Dv2 tiled <https://e3d.readthedocs.io/en/e3dinv_ver2_tiled/index.html#e3d-version-2-tiled-package>`_
- `TDoctree v2 <https://tdoctree.readthedocs.io/en/tdoctree_ver2/>`_

.. figure:: ../../../../images/object/data/em/EM3DSoundingOffsets.png
    :align: center
    :scale: 75%


