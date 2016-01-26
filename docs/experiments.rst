Experiments
===========

.. warning:: This contains broad overview of software pipeline used for various experiments in the lab.  Note that this documentation does not dive deep into any one software package, it merely contains recipes for conducting analysis-heavy experiment in MATLAB.

Electrophysiology in freely behaving songbirds using the Intan system
---------------------------------------------------------------------

Both the RHA and RHD versions of the Intan system are supported through various packages.  It is assumed that all recordings are performed in freely behaving animals, though various parts of the pipeline work perfectly well with other data types.  Here is the broad overview, with the code used for each step.

#.  Data is acquired on a "front-end" machine using the `RHA/RHD evaluation software <http://intantech.com/downloads.html>`_.  This is not resource intensive, most modern Intel machines with 3 GBs of RAM have worked fine.  PCs are simplest, but Linux/OS X will work just fine if you're willing to compile the Intan software.    
#.  Raw data files are then transfered to a "back-end" machine where all offline analysis is performed using a `simple bash script <https://github.com/jmarkow/data-handling>`_.  
#.  Once the files are transfered, processing begins with song detection. Files are processed for song and the resulting data is organizing using the `intan_frontend <https://github.com/jmarkow/intan_frontend>`_.  
#.  The user then selects a template from the song extractions.  Alignments to the template are performed using `zftftb <https://github.com/jmarkow/zftftb>`_.
#.  After alignments are performed, all further analysis is automated using the `robofinch framework <https://github.com/jmarkow/robofinch>`_. 
#.  Spike sorting is performed using `spikoclust <https://github.com/jmarkow/robofinch>`_.  

Now each of the steps in detail...   


Fiber photometry in freely behaving songbirds
---------------------------------------------


