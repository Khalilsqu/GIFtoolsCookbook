.. _AtoZNS_index:

.. include:: <isonum.txt>


From EDI Files to Inverting Natural Source EM Data
==================================================

This A to Z example tackles practical aspects of preparing and inverting natural source EM data (MT and/or ZTEM) using GIFtools.
Here the user begins with a set of EDI formatted MT survey files, loads them into the GIFtools framework, interprets the data and inverts the data with two different OcTree codes (E3DMT versions 1 and 2).
The goal is to use synthetic high frequency MT data to resolve the D0-27 and D0-18 anomalies.
We then add ZTEM data and show the capability of GIFtools to jointly invert multiple datasets.
Once finished, the user will be familiar with:

	- The coordinate systems and Fourier convention generally used for MT data
	- Basic interpreting of MT data through apparent resistivities
	- Practical strategies for inverting natural source data with the E3DMT codes
	- Differences between E3DMT versions 1 and 2
	- How to jointly invert MT and ZTEM data using GIFtools

The full A to Z example is split into 3 parts:

.. toctree::
    :maxdepth: 1

    Loading, interpreting and preparing data <data>
    MT inversion <mt_inversion>
    ZTEM inversion <ztem_inversion>





