====================
Artifact PonyExpress
====================

.. image:: https://travis-ci.org/gpuoti/Artifact-PonyExpress.svg?branch=master
    :target: https://travis-ci.org/gpuoti/Artifact-PonyExpress

.. image:: https://www.codetriage.com/gpuoti/artifact-ponyexpress/badges/users.svg
    :target: https://www.codetriage.com/gpuoti/artifact-ponyexpress
The pony helps you trade software or data modules!
It is a general purpose package and dependency system that aims to be simple and fast. It is not constrained to any build system or language even if it was designed with native C++ development and Scons in mind.

Install
-------

Pony is a python powered program, it can be installed using pip.

.. code-block:: bash

    > pip install pony-express
    

pip package build instructions
------------------------------

To build the pip package from source run this command:

.. code-block:: bash

    > python setup.py sdist --format=gztar  

Any additional dependency shall be listed into the setup.py script in order to let pip resolve those dependencies at installation time.


run tests
---------

If you (this is also a reminder for myself) are interested in making changes to the source code, put in place some tests too, and make sure the tests pass still after your modifications running:

.. code-block::
    
    > py -3.5 -m unittest
    

documentation
-------------

pony is documented using **restructuredText** and **sphinx**. Documentation source files are in doc/source folder. To build the documentation run the following command after cd to the project's documentation root folder.

.. code-block:: bash

    > make  html
    

The output will be accessible from  doc/user-doc/html/pony.html. Of course you can build documentation using any format supported by sphinx.


Project statisticts
-------------------

Together with source file is stored also some source code measurements taken from time to time. Here are instructions to collect statistics into the database and to view some graphics made from that data.
Assuming cloc is available on your development (or build) machine as as PyGeek. To collect cloc statistics:

.. code-block:: bash

    > cloc --xml --out cloc_xml_out.xml .


Just remember to remove any build output into the project folder when you launch the statistics collect command. Once you have that xml file, you have to join it into the historical database using PyGeek scripts.

.. code-block:: bash
    
    > py -2.7 StoreClocStats.py
    adding stats from cloc_xml_out.xml to cloc_stats_sotage.json


Unfortunatly Pygeek still is not compatible with python 3.5 so, once you have your newly created statistics into the cloc stats database, you can view the results using Pygeek scripts again.

.. code-block:: bash

    > ShowClocStats.py
    
.. image:: doc/source/img/loc_stats.png

