.. _objectFunctionalityWorkflowDOICalc:

.. include:: <isonum.txt>

Depth of investigation (DOI) calculation
========================================

With the ``DOI`` Workflow, the user can compare two models in order to
estimate the robustness of geophysical anomalies. The resulting DOI index can be
visualized and used as weights in subsequent inversions.

.. figure:: ../../../images/createInversionWorkflowDOI.png
    :align: center
    :width: 400

**Create** |rarr| **Workflow** |rarr| **DOI calculation**


.. _objectFunctionalityWorkflowDOIEdit:

Edit Options
^^^^^^^^^^^^

DOI calculations follow the work presented in `Li & Oldenburg 1999 <http://www.eos.ubc.ca/ubcgif/pubs/papers/geop64-403.pdf>`_.
The calculation requires two models and their respective reference values.

.. figure:: ../../../images/Workflows/DOI_options.png
    :align: center
    :figwidth: 40%

OPTION 1: Cell-by-cell
----------------------

The first method looks at the deviation of models normalized by the difference
in reference value on a cell-by-cell basis:

.. math::

	R(x,y) = \frac{m_1(x,z) - m_2(x,z)}{m_1^{ref}-m_2^{ref}}

where :math:`m_1` and :math:`m_2` are the two chosen models and
:math:`m^{ref}_1` and :math:`m^{ref}_2` their respective background reference
models. Model parameters with large R values are assign high credibility.

OPTION 2: Cross-correlation
---------------------------

The second strategy measures the difference between two images over `n` cells in a rectangular window.
The cross-correlation between the two models are calculated as

.. math::

	C = \frac{ \sum_i^N (m_{1_i}-\bar m_{1}) (m_{2_i}-\bar m_{2})}{\bigg( \sum_i^N (m_{1_i}-\bar m_{1})^2 \sum_i^N (m_{2_i}-\bar m_{2})^2\bigg)^{(1/2)}}


where :math:`\bar m` is the average of the model over the window.
The DOI index is calculated by

.. math::
	R = \frac{C-1}{2}
